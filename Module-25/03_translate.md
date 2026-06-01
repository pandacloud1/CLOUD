## AMAZON TRANSLATE
- This hands-on is used to create a website to translate `English` to `Hindi`
- Website is created using S3. In the backend, API Gateway is configured to trigger Lambda
- Lambda will get the translation done using Amazon Translate

### Step 1: Create Lambda
- Configuration: Timeout: `30 sec`
- Permissions: IAM Role: Add policies: `TranslateFullAccess`
```python
import json
import boto3

translate = boto3.client('translate')

def lambda_handler(event, context):

    body = json.loads(event['body'])

    english_text = body['text']

    response = translate.translate_text(
        Text=english_text,
        SourceLanguageCode='en',
        TargetLanguageCode='hi'
    )

    translated_text = response['TranslatedText']

    return {
        'statusCode': 200,
        'body': json.dumps({
            'translated_text': translated_text
        })
    }
```

### Step 2: Create API Gateway
- Integration: `<Add Lambda function>`
- Route: `POST /textract`
- CORS:
  - Allow Origin: `*`
  - Allow Headers: `Content-Type`
  - Allow Methods: `POST` & `OPTIONS`
- Copy `<API-Invoke-URL>` and use it in your `index.html` file

### Step 3: Create S3 bucket (for Website)
- Create a public bucket and allow ACL
- Create `index.html` file & add `<API-Invoke-URL>` & upload the file
- Make `index.html` file public using ACL
- Access your S3 website and do the testing to convert `English` to `Hindi`
```html
<!DOCTYPE html>
<html>
<head>
    <title>AWS Translate Demo</title>
</head>
<body>

<h2>English to Hindi Translator</h2>

<textarea id="inputText"
rows="5"
cols="50"
placeholder="Enter English text"></textarea>

<br><br>

<button onclick="translateText()">
Translate
</button>

<h3>Hindi Translation</h3>

<pre id="output"></pre>

<script>

async function translateText() {

    const text =
        document.getElementById("inputText").value;

    const response =
        await fetch(
        "<API-Invoke-URL>/translate",
        {
            method: "POST",
            headers: {
                "Content-Type": "application/json"
            },
            body: JSON.stringify({
                text: text
            })
        });

    const result = await response.json();

    document.getElementById("output")
        .textContent =
        result.translated_text;
}

</script>

</body>
</html>
```
