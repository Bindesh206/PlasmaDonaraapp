# PlasmaDonaraapp
# lambda Function for retriviving the data
import boto3
dynamoDB = boto3.resource('dynamodb')
table = dynamoDB.Table('student')

def lambda_handler(event,context):
    rollnumber=event['rollnumber']
    print(rollnumber)
    resp = table.get_item(Key={"rollnumber":rollnumber})
    return resp['Item']
    
    
    
    #data access
    "email": "$input.params('email')"
