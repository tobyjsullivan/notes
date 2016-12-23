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
