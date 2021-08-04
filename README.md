# Project 5 - Cloud DevOps Engineer Capstone Project
In this project, I applied my skills and knowledge which was developed throughout the Cloud DevOps Nanodegree program.

# Objetive
Redirect traffic from the blue container to the green container
![1_7fCmf1DMXS7anjS-dQWxnw](https://user-images.githubusercontent.com/75679079/128158903-ba552218-b305-4da4-a8cb-535a0292111b.jpeg)
# Project Tasks:
Working in AWS
Using Jenkins to implement Continuous Integration and Continuous Deployment
Building pipelines
Working with CloudFormation to deploy clusters
Building Kubernetes clusters
Building Docker containers in pipelines

# Project Requirement:
To be able to use this CI/CD pipeline you will need :
Circleci
Docker
Pip
AWS Cli
Eksctl
Kubectl

# Instructions
#### 1.Build the blue image from the blue folder. Adjust the name of the image to your own.
```./run_docker.sh```

#### 2. Push the image to docker hub from the blue folder. Adjust the name of the image to your own.
```./upload_docker.sh```

#### 3. Build the green image from the green folder. Adjust the name of the image to your own.
```./run_docker.sh```

#### 4. Push the image to docker hub from the green folder. Adjust the name of the image to your own.
```./upload_docker.sh```

#### 5. Start minikube to create the cluster
```minikube start```

#### 6. Create a replication controller blue pod
```kubectl apply -f ./blue-controller.json```

#### 6. Create a replication controller green pod
```kubectl apply -f ./green-controller.json```

#### 7. Create the service, redirect to blue and make it externally visible, we specify "type": "LoadBalancer"
```kubectl apply -f ./blue-green-service.json```

#### 8. Get the URL of the service by running
```minikube service bluegreenlb --url```

#### 9. You can now open the website blue in your browser by using the URL in the previous step

#### 10. Update the service to redirect to green by changing the selector to app=green

#### 11. Implement the changes
```kubectl apply -f ./blue-green-service.json```

#### 12. Get the URL of the service by running
```minikube service bluegreenlb --url```

#### 13. You can now open the website green in your browser by using the URL in the previous step
