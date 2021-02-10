Activity (Setup VPN with two GCP custom mode Networks)
Create VPN connection between two GCP custom mode VPC networks and test connectivity between two different instances located in diffrent networks

Steps performed :

1.Create two projects (project-1 , project-2) in two different regions(us-central1 ,asia-east1)
2.Create two VPCs (pratik-vpc-1 ,pratik-vpc-2) in both projects respectively
3.Create firewalls in both VPCs
4.Create two VM instances (vm-instance-project-1 ,vm-instance-project-2) in both projects respectively
5.Create static IP address (static-ip1 , static-ip2) in both project
6.Create two cloud routers (cloud-router1 ,cloud-router2) in both projects with two different Google ASN numbers
7.Create two VPN gateways(vpn-gateway1 ,vpn-gateway2)
8.Create VPN tunnel 1 in project-1 , Enter Remote Peer IP of static-ip2 , select routing option as Dynamic routing and create BGP session
9.Create VPN tunnel 2 in project-2 , Enter Remote Peer IP of static-ip1 , select routing option as Dynamic routing and create BGP session
10.Now SSH into any VM and Ping another VM
11.Packets should be received.

