# Pratik-GCP-Training

Activity 1.1 (Deploying web application on compute engine instance)

Steps performed:
1. Enable deployment manager API
2. Deployment manager YAML file is created to create VM instance. You can refer configfile.yaml 
3. pratik-vpc is created
4. Firewall is created for VPC network
5. SSH into created VM 
6. Nginx server is installed 
7. Changes are made in nginx-debian.html file
8. Using external ip the page is checked whether changes are reflected or not.

Activity 1.2 (Add high avaialbilty and scalabilty to the existing app deployed in compute engine)
 steps performed:
 
 1.create instance template and two manage instance groups with min. instance 1 and max. instance 3
 2.create load balancer and add two MIGs as backends.
 3.create vm instance using instance template in us-central1-a zone
 4.create vm instance using instance template in us-central1-b zone
 
 For checking autoscaling:
 
 1.Install nginx server on one of the MIGs
 2.Add python script and cpu limit tool 
 3.Run the python file
 4.now cpu utilization limit gets exceed and new vm is created
 
 For checking high availability:
 1.As we have 2 instances in two different zones both with nginx server installed
 2.Now delete one of the instance from one zone
 3.Now check hitting same ip adrress which will redirect to another instance in zone
 4.so there wont be any downtime .
 
 
