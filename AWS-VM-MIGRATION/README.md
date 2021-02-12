Activity (Migration from AWS to GCP ( Statefull Virtual Machines))

Steps performed :

Prerequistes:
1.You should have EC2 instance created in AWS
2.You should have S3 bucket in AWS
3.You should have Cloud storage bucket
4.Enable cloud build API

A.Export an existing AWS vm in .ova format
  1.To export your instance, use the create-instance-export-task command.
  
    aws ec2 create-instance-export-task --description "RHEL5 instance" \
    --instance-id i-1234567890abcdef0 --target-environment vmware \
    --export-to-s3-task DiskImageFormat=vmdk,ContainerFormat=ova,S3Bucket=myexportbucket,S3Prefix=PK
    
  2.Stop your EC2 vm instance. To get instance in .ova format in your S3 bucket (It will take 10 min)
    
B.Copy the .ova file to Google cloud storage bucket from AWS S3 Bucket
  1.Login to GCP console Select "Data transfer for cloud" service.
  2.Create a transfer
  3.Select source as AWS S3 bucket
  4.Enter Access key ID and Secret access key (Create user in AWS and Give it S3bucketfullaccess and Copy the Access key ID and Secret key)
  5.Enter destination bucket as cloud storage storage bucket path
  6.Configure the transfer.
  7.The .ova file should be transferred in Cloud storage bucket.
  
C.Import the .ova file to Google cloud from cloud storage bucket
  1.To import an OVA file from Cloud Storage to Compute Engine, use the gcloud compute instances import command.
      gcloud compute instances import [INSTANCE_NAME] --source-uri=gs:[PATH_TO_OVA_FILE] --os=[Ex. ubuntu-2004] --network=[network-name]
  2. This will take around 30 to 40 min based on your .ova file size
  
D.Just connect to the Google cloud machine and confirm its identical to the VM you started with.
  1.Check the status in Cloud Build Logs.
