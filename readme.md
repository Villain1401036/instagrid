aws lambda function - 

Prereqisites -
   aws cli installed and configured
   terraform installed              
   aws access key and secret
    #since its a simple example we are using a normal authentication not SSO and for production we should have strict permissions


event invocation using this json schema 
{
    "device":"Asdasd",
    "payload":"F1E6E63676C75000"
}

the function is in the folder ./functions/batterydata/main.py

to run the example - steps 
 1> fill the <> with approprite values in file providers.tf - aws_secret_token , aws_access_key , region 
 2> execute "terraform init"
 3> execute "terraform plan -var="env_name=dev""  -- for dev env planing this does not create the lambda on the aws account
 4> terraform apply -var="env_name=dev"           -- for applying the planned infra on aws cloud

to use the eventhandler we can use a Kafka , or kinesis to feed the event to handlers -- 

to test the function an instagrid.ipynb file is attached (just run and see the result).  