# aws-scaleio
A project to stand up a ScaleIO cluster in AWS, for testing against EMC {code} projects. 

This template uses a custom AMI image. You've been warned!

*Usage*

Launch this template *in the US-West-1 (aka N.California) region* using AWS Cloudformation. 

Using the AWS web gui, in the services selection window:
 - click 'Cloudformation' under 'Management Tools'
 - click 'Create Stack', then 'Choose a Template'
 - click 'Upload file to S3', and upload the .json file from this repo
 - give the stack a name (like ScaleIOTesting or something)
 - select a keypair that exists in the N.California region!
 - alter the ssh source CIDR if you like, or don't
 - click next, add tags if you want, or don't, then click next
 - review your settings and click 'Create' to create the stack

The stack will take approximately two minutes to build, and then should be available for login.

To launch this stack using AWS commandline tools, use a commandline similar to the following:

```
[user@host] ~/ $ aws cloudformation create-stack --stack-name ScaleIOTesting --template-body file:////home/ME/dev/aws-scaleio/ScaleIO_Testing_Cluster.json --parameters ParameterKey=KeyName,ParameterValue=MYKEY
```
