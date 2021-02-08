Activity (Patching VM and Install a software package)

Create Virtual Machines with Private IP only on non default VPC . Download and install some software from internet and patch the VM

Steps performed:

1.Create vpc (pratik-vpc) 
2.Create firewall (pratik-firewall)
3.Create vm (pratik-instance-1) with no external ip address
4.Create vm (pratik-instance-2) with external ip address
5.Create NAT Gateway(pratik-nat) - It lets VM without external IP addresses send outbound packets to internet and receive inbound packets.
6.Create router (pratik-router)
7.Now SHH into vm pratik-instance-2
8.To Get into pratik-instance-1 Type - SSH pratik-instance-1
9.Now Install nginx using command - sudo apt-get install nginx
10.Enable external ip to check whether nginx is installed or not on pratik-instance-1   
11.Hit external IP of pratik-instance-1 to see nginx welcome page.
