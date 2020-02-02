# Udagram Image Filtering Microservice

Udagram is a simple cloud application developed alongside the Udacity Cloud Engineering Nanodegree. It allows users to register and log into a web client, post photos to the feed, and process photos using an image filtering microservice.

The project is split into three parts:
1. [The Simple Frontend](/udacity-c3-frontend)
A basic Ionic client web application which consumes the RestAPI Backend. 
2. [The RestAPI Feed Backend](/udacity-c3-restapi-feed), a Node-Express feed microservice.
3. [The RestAPI User Backend](/udacity-c3-restapi-user), a Node-Express user microservice.

## Tasks
###Setup Docker Environment
You'll need to install docker https://docs.docker.com/install/. Open a new terminal within the project directory and run:
1. Switch the folder
```$xslt
cd udacity-c3-deployment/docker
```
2. Build & Push the images
```$xslt
docker-compose -f docker-compose-build.yaml build --parallel
docker-compose -f docker-compose-build.yaml push
```
3. Run the container
```$xslt
docker-compose up
```
###Setup k8s Environment
1. Create the cluster
```$xslt
eksctl create cluster --name udagram
```

2. Create travis-user
```$xslt
eksctl create iamidentitymapping --name udagram --role arn:aws:iam::?:role/travis_salah --group system:masters --username travis_salah
```

3. run the ci/cd-pipeline
