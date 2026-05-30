```py
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
