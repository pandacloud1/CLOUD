## EVENTBRIDGE HANDS-ON
- This hands-on will notify the user for EC2 state change
- We will integrate multiple services like EC2, CloudTrail, S3, EventBridge, Lambda, CloudWatch, SNS in this demo

### Architecture
<img width="894" height="598" alt="image" src="https://github.com/user-attachments/assets/2c3181b2-f8f8-4b7e-8560-7c41522510b4" />

### Step 1: Create an EC2 instance
- Create an EC2 instance with an instance type & default config

### Step 2: Create CloudTrail
- Create custom trail from CloudTrail
- Use S3 bucket as the destination

### Step 3: Create Lambda
- Create Lambda function & add below code
- Change timeout to `30 sec` to avoid timeout issues

```python
import json

def lambda_handler(event, context):

    instance_id = event['detail']['instance-id']
    state = event['detail']['state']

    print('EC2 State Change Detected')
    print(f'Instance ID: {instance_id}')
    print(f'Current State: {state}')

    print('Full Event:')
    print(json.dumps(event, indent=2))

    return {
        'statusCode': 200,
        'body': f'Instance {instance_id} changed state to {state}'
    }
```

### Step 4: Create SNS topic
- Create topic → Standard → (Give name) → Create topic
- Subscriptions → Create subscription
- Protocol: `Email`
- Endpoint: `(Add email address)`
- Subscribe to the topic received on mail

### Step 5: Create EventBridge
- Create EventBridge Rule → Create Rule → Advanced builder
- Event pattern 
  - Event source: `AWS services` 
  - AWS service: `EC2`
  - Event type: `EC2 Instance State-change Notification`
  - Event Type Specification 1: `Any state`
- Select target(s)
  - Target 1: AWS service: `Lambda function` (Select your function)
  - Add another target
  - Target 2: AWS service: `SNS topic` (Select your topic)
 
### Step 6: Testing
- You can view the logs in CloudWatch logs for EC2 state change
- You can manually change EC2 state (if required) & get mail notifications

### Deleting steps
- Delete EC2
- Delete CloudTrail
- Delete S3
- Delete EventBridge rule
- Delete Lambda
- Delete CloudWatch → Logs management: Log group
- Delete SNS topic
