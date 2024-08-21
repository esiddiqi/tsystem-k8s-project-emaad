



# Bookstore Application Deployment

## Resources Created

### 1. Dockerfile
- A Dockerfile has been created to build the image from the code provided in the `/app` directory.

### 2. Docker Image
- The Docker image has been built and pushed to Docker Hub.

### 3. Deployment
- Deployments have been created for both the main application and PostgreSQL.

### 4. Service
- **NodePort**: Created for the main application to expose it on a specific port.
- **ClusterIP**: Created for PostgreSQL to allow internal communication within the Kubernetes cluster.

### 5. ConfigMap
- A ConfigMap has been created to pass environment variables required for the database parameters into the container.

### 6. Secrets
- Secrets have been created to securely store and manage database credentials.

## Issues Encountered

- **Dependency Issues**: There were issues in the `requirements.txt` file, which were resolved by editing the file to avoid dependency conflicts.
- **GET Request Error**: While performing a GET request, the DB connection works fine; however, there's a `JSONResponse` serialization error:
  ```json
  {
    "message": "Object of type JSONResponse is not JSON serializable"
  }

  This seems to be related to the code.

## Testing

- Testing has been performed by deploying the application on a local machine as a standalone container.
- The application was later deployed on Minikube for further testing.
- Tried Docker-compose as well , Application is accessible , however connectivity to DB has issues

## Accessing the Application

The application can be accessed using the following URL:  
[http://localhost:80/docs](http://localhost:80/docs)



Thanks, 
### Emaad Siddiqi












################################################################################

# DevOps Engineer Assignment

A junior developer has given you his code for a bookstore API, and he claims that 
the client (a bookstore) insists it's deployed on our k8s cluster, otherwise they will not pay
for all the hard work you and your developer coworkers have done. 

Your job is to prepare this API to be deployed on a Kubernetes cluster and <em>(optionally)
for easier local development as a containerized application.</em>

### The application needs:  
- to be safe as possible
- run in multiple containers with all its dependencies
- to have easily adjustable settings (or parameters)
- to have an option to directly view (or edit) raw data in the backend database
- (optionally) to be easily tested in a local environment
without k8s installed

Good luck and have fun!