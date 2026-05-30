## AMAZON REKOGNITION HANDS-ON
- Image Analysis Using Amazon Rekognition, Lambda, S3 & DynamoDB
- We have two codes, one for image labels and other for celebrity recognition
<img width="679" height="323" alt="image" src="https://github.com/user-attachments/assets/ed607f2c-7f15-4015-af53-ea253f511152" />

### 1. Create a S3 bucket
Keep all the settings as default

### 2. Create DynamoDB table
- Give name: `rekognition-table`
- Partition key: `ImageName` → Create table

### 3. Create Lambda
- Give name: `rekognition-lambda`, Add Runtime: `Python 3.14` or `latest` & add below given code → `DEPLOY`
- In the code, update the DynamoDB table name to `rekognition-table`
- Increase execution time: Lambda → Configuration → Timeout settings → Change to `30 secs`
- Add permissions in the role: Lambda function → Configuration → Open the default role created → Attach policies → Add below
  - RekognitionFullAccess
  - DynamoDBFullAccess
  - S3ReadOnlyAccess
- Now add trigger for S3: Lambda → Add trigger → Source: S3 → Select bucket → Keep all default → Acknowledge → Create trigger

### 4. Testing
- Upload some images from your system, wait for sometime, the results will get populated in DynamoDB table.
- It will give information like:
  - type: Food
  - Confidence: 99%
  - category
  - Celebrity info


### IDENTIFY IMAGE LABELS
- Code explanation:
  - Image is uploaded to S3
  - Lambda function automatically sends the image to Amazon Rekognition, extracts detected labels
  - Results are stored in DynamoDB table.
```py
# boto3 is official AWS library for Python
import boto3
import json

# AWS automatically calls this function when the Lambda is triggered
def lambda_handler(event, context):
    # Initialize clients (AWS connection points)
    s3_client = boto3.client('s3')
    rekognition_client = boto3.client('rekognition')
    dynamodb = boto3.resource('dynamodb')
    # Connect to DynamoDB Table
    table = dynamodb.Table('rekognition-table')  # Replace with your table name

    # Read S3 Event Information
    # Get the S3 bucket name and object key from the event
    bucket_name = event['Records'][0]['s3']['bucket']['name']
    object_key = event['Records'][0]['s3']['object']['key']

    # Call Amazon Rekognition (to detect labels in the image)
    response = rekognition_client.detect_labels(
        Image={'S3Object': {'Bucket': bucket_name, 'Name': object_key}},
        MaxLabels=10
    )

    # Store the labels detected in DynamoDB
    labels = [{'Confidence': label['Confidence'], 'Name': label['Name']} for label in response['Labels']]
    table.put_item(
        Item={
            'ImageName': object_key,
            'Labels': json.dumps(labels)
        }
    )
    # Return Success Message
    return {
        'statusCode': 200,
        'body': json.dumps('Image processed successfully!')
    }
```

### IDENTIFY CELEBRITIES
```py
import boto3
import json

def lambda_handler(event, context):

    rekognition = boto3.client('rekognition')
    dynamodb = boto3.resource('dynamodb')
    table = dynamodb.Table('rekognition-table')   # Replace with your table name

    bucket_name = event['Records'][0]['s3']['bucket']['name']
    object_key = event['Records'][0]['s3']['object']['key']

    response = rekognition.recognize_celebrities(
        Image={
            'S3Object': {
                'Bucket': bucket_name,
                'Name': object_key
            }
        }
    )

    celebrities = [
        {
            'Name': celeb['Name'],
            'Confidence': celeb['MatchConfidence']
        }
        for celeb in response['CelebrityFaces']
    ]

    table.put_item(
        Item={
            'ImageName': object_key,
            'Celebrities': json.dumps(celebrities)
        }
    )

    return {
        'statusCode': 200,
        'body': json.dumps('Celebrity detection completed!')
    }
```
