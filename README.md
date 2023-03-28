# kaiburr_assignment--TASK-3-
Task 3. Kubernetes.
Use the application that you created in task #1 or task #2. Create dockerfiles and build docker
images. Create kubernetes yaml manifests for the application (at least a deployment and a
service). It’s ok to expose the application with a LoadBalancer or NodePort service or with an
ingress. Spin up a single-node local Kubernetes cluster (Docker Desktop, Kind or Minikube) or
use a managed cluster like EKS, AKS, GKE etc. Deploy MongoDB to the cluster (it’s ok to use a
community helm chart for this, any other approach is fine as well). Then deploy the application
to the cluster by applying your manifests. The following requirements should be fulfilled:
● you can bring your application up by applying your yaml manifests
● mongodb is running in a separate pod
● the application should take mongo connection details from the environment variables
● the app endpoints should be available from your host machine
● a persistent volume should be used to store the MongoDB data. I.e., when you delete
the MongoDB pod the records in the db should not disappear

# STEPS FOR THE SOLUTON

To complete Task 3, we will follow the following steps:

    Create Dockerfiles and build Docker images for the Java REST API application from Task 1 and the Swagger-generated Java REST API from Task 2.
    Create Kubernetes YAML manifests for the application and MongoDB.
    Deploy MongoDB to the cluster.
    Deploy the Java REST API application to the cluster.
    Test the application by making requests using an HTTP client.
    
Step 1: Create Dockerfiles and build Docker images
We will create Dockerfiles for both the Java REST API application and the Swagger-generated Java REST API. We will use the following Dockerfile for both applications:

    FROM openjdk:11-jre-slim
    WORKDIR /app
    COPY target/*.jar /app/app.jar
    CMD ["java", "-jar", "/app/app.jar"]
    
Assuming that we have built the applications using Maven and that the compiled JAR files are located in the target directory, we can build the Docker images with the following commands:

For the Java REST API application:

    docker build -t java-rest-api-app .

For the Swagger-generated Java REST API:

    docker build -t swagger-java-rest-api-app .



Step 2: Create Kubernetes YAML manifests
We will create Kubernetes YAML manifests for the application and MongoDB. We will create two separate YAML files: one for MongoDB and one for the Java REST API application.
both yaml codes are uploded.


Step 3: Deploy MongoDB to the cluster
We will deploy MongoDB to the cluster using the YAML manifest for MongoDB that


















