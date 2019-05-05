# AWS CLI

## Installation and Configuration

```
pip install awscli

aws configure
```

## Usage

### DynamoDB

#### List tables

```
aws dynamodb list-tables
```

### Creating a table

```
aws dynamodb create-table --table-name '[TABLE_NAME]' --attribute-definitions 'AttributeName=ID,AttributeType=S' --key-schema 'AttributeName=ID,KeyType=HASH' --provisioned-throughput 'ReadCapacityUnits=1,WriteCapacityUnits=1'
```

### IAM

#### Create a policy

```
POLICY_DOCUMENT='{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "Stmt1482536860052",
      "Action": [
        "dynamodb:BatchGetItem",
        "dynamodb:GetItem",
        "dynamodb:PutItem",
        "dynamodb:Query",
        "dynamodb:Scan"
      ],
      "Effect": "Allow",
      "Resource": "[RESOURCE_ARN]"
    }
  ]
}'
aws iam create-policy --policy-name '[POLICY_NAME]' --policy-document "$POLICY_DOCUMENT"
```

#### Delete a policy

```
aws iam delete-policy --policy-arn '[POLICY_ARN]'
```

#### List locally managed policies (exclude AWS-managed)

```
aws iam list-policies --scope Local
```

#### Create a user

```
aws iam create-user --user-name '[USER_NAME]'
aws iam create-access-key --user-name '[USER_NAME]'
```

#### Attach policy to user

```
aws iam attach-user-policy --user-name '[USER_NAME]' --policy-arn '[POLICY_ARN]'
```
