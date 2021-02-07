Activity 2.1 (Deploy microservice app with UI, Backend service and a DB service on GKE cluster)
  
1.Create VPC (pratik-vpc) using console
2.Create kubernetes cluster with 3 nodes (pratik-cluster-1)
3.To retrieve cluster credentials and configure kubectl command-line tool 
  command- gcloud container clusters get-credentials guestbook --zone us-central1-a
4.Create 6 YAML files
   1.guestbook-frontend.yaml                (File describes the deployment for guestbook app web server)
   2.guestbook-frontend-service.yaml        (File specifies the load balancer to access app over internet)
   3.redis-leader-deployment.yaml           (For Backend Redis)
   4.redis-leader-service.yaml              (To communicate with redis leader to write its data i.e. proxy the traffic to redis leader pod)
   5.redis-follower-deployment.yaml         ( File describes deployment for Redis slave)
   6.redis-follower-service.yaml            (To make application to communicate with redis slave)
5.Now using load balancer ip we can access guestbook app over internet.

Activity 2.2 (Enabling Autoscaling, High Availability)

1.You can use command to scale the front end deployments
  command- kubectl scale deployment frontend --replicas=8
2.For high availabilty you can make your cluster regional and select multiple zone while cluster creation.


Activity 2.3 (Perform Rolling update to above Deployment)

1.Change the version of image on one of the container
   command- kubectl set image deployment redis-master master=redis:2.0
2.Check the rollout status of container
   command-kubectl rollout status deployment redis-leader
3.Verify the output to check whether update is made or not
