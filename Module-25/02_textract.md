

# AWS Textract 
- Extract text from image using S3 Static Website, API Gateway, Lambda and Textract
- In real time, use CloudFront to add S3 as origin, so that you do not need to create a public bucket

### Architecture
<img width="606" height="202" alt="image" src="https://github.com/user-attachments/assets/cf59823d-4930-42bd-825b-42049c50cb12" />

### Step 1: Create S3 Bucket for Static Website
- S3 → Allow Public Access → Create Bucket
- Enable Static Website Hosting: Bucket → Properties → Static Website Hosting

### Step 2: Create Lambda Function
- Lambda → Create Function
- Runtime: Python 3.14
- Lambda → Configuration → General Configuration → Timeout: 30 seconds
- Attach IAM Permissions: Lambda → Configuration → Permissions
  - AmazonTextractFullAccess
  - AmazonS3FullAccess
- Add Lambda Code → Deploy
- Ref: [https://docs.aws.amazon.com/boto3/latest/reference/services/textract.html]

```python
import boto3
import base64
import json

textract = boto3.client('textract')

def lambda_handler(event, context):

    body = json.loads(event['body'])

    image_bytes = base64.b64decode(body['image'])

    response = textract.detect_document_text(
        Document={
            'Bytes': image_bytes
        }
    )

    extracted_text = ""

    for item in response['Blocks']:
        if item['BlockType'] == 'LINE':
            extracted_text += item['Text'] + "\n"

    return {
        'statusCode': 200,
        'headers': {
            'Access-Control-Allow-Origin': '*'
        },
        'body': json.dumps({
            'text': extracted_text
        })
    }
```

### Step 3: Create API Gateway
- API Gateway → Create API → HTTP API
- API Gateway → Integrations → Integration Type: Lambda → Function: <Add your Lambda function>
- Create Route: API Gateway → Routes → Method: POST → Path: /extract
- Attach the Lambda integration.
- Configure CORS: API Gateway → CORS
  - Access-Control-Allow-Origin: `*`
  - Access-Control-Allow-Headers: `Content-Type`
  - Access-Control-Allow-Methods: `POST` & `OPTIONS`
- Get Invoke URL: API Gateway → Stages → $default
- Copy the Invoke URL & add it in S3 index.html file with `/extract` as suffix.
```text
# Example
https://nqy12gcem5.execute-api.us-east-1.amazonaws.com
```

### Step 4: Create Frontend Website
- Create a file: `index.html`
- Add below code → Make the index.html file public using ACL
```html
<!DOCTYPE html>
<html>
<head>
    <title>Textract Demo</title>
</head>
<body>

<h2>Upload Image</h2>

<input type="file" id="file">

<button onclick="extractText()">
Extract Text
</button>

<pre id="output"></pre>

<script>

async function extractText(){

    const file =
        document.getElementById('file').files[0];

    const reader = new FileReader();

    reader.onload = async function(){

        const base64 =
            reader.result.split(',')[1];

        ## ADD YOUR API INVOKE URL HERE
        const response =
            await fetch(
            '<YOUR_API_GATEWAY_URL>/extract',
            {
                method:'POST',
                headers:{
                    'Content-Type':'application/json'
                },
                body:JSON.stringify({
                    image:base64
                })
            });

        const result =
            await response.json();

        document.getElementById('output')
            .textContent = result.text;
    }

    reader.readAsDataURL(file);
}

</script>

</body>
</html>
```
- Access the Website
- Upload an image containing text → Extract → The extracted text is displayed directly on the website.
- Right click on website → Inspect → Network → Check logs here
- Additionally you can check logs in CloudWatch → Lambda → Monitor → View CloudWatch logs

### Learning Outcomes
By completing this demo, you learn:
- S3 Static Website Hosting
- API Gateway HTTP APIs
- Lambda Integrations
- CORS Configuration
- Amazon Textract OCR
- Serverless Architectures
- Frontend and Backend Integration
- Base64 Image Processing
- API Testing and Troubleshooting
