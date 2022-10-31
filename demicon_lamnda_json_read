import awswrangler as awswrangler
import json
import jsonpath-ng

def lambda_handler(event, context):
    
    bucket = event ['detail']['bucket']['name']
    s3_key = event ['detail']['object']['key']
    json_file = 's3://' + bucket + '/' + s3_key
    data = awswr.s3.read_json(path=json_file)
    data_output= "parsing data with jsonpath for outputs - $.outputs.lb_url.value or $.outputs.[?(@.name=="lb_url")].value"
    return {
        'statusCode': 200,
        'body': json.dumps(data_output)
    }