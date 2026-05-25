# CLOUDFORMATION

## AWS Templates
- Ref: [https://docs.aws.amazon.com/AWSCloudFormation/latest/TemplateReference/aws-template-resource-type-ref.html]

## CREATE EC2 INSTANCE
- SELECT REGION: N VIRGINIA
- Below code will create `EC2 instance` along with a `Security group`

```yaml
Resources:
  MySecurityGroup:
    Type: AWS::EC2::SecurityGroup
    Properties:
      GroupDescription: Allow SSH and HTTP access
      SecurityGroupIngress:
        - IpProtocol: tcp
          FromPort: 22
          ToPort: 22
          CidrIp: 0.0.0.0/0
        - IpProtocol: tcp
          FromPort: 80
          ToPort: 80
          CidrIp: 0.0.0.0/0

  MyEC2Instance:
    Type: AWS::EC2::Instance
    Properties:
      InstanceType: t2.micro
      ImageId: ami-0236922087fa98b6e  # Amazon Linux 2023
      SecurityGroupIds:
        - !Ref MySecurityGroup
      KeyName: Linux-key              # Your key pair name
      Tags:
        - Key: Name
          Value: MyServer
```

## DELETE EC2 INSTANCE
- Delete EC2 instance after Lambda practical
```txt
CloudFormation → Select Stack → Delete
```
