Activity : Deploy static website on cloud storage

Steps performed:

1.Create cloud storage bucket (pratik-bucket) with multiregional , Standard storage class , fine grained access control
2.Create index.html file
3.Upload index.html file to pratik-bucket.
4.To make content of bucket public to internet edit permissions 
5.Use below command to give public access to all users
  Command - gsutil -m acl ch -r -u Allusers:R gs://pratik-bucket/*
6.Copy the public access URL and test it to see index.html
