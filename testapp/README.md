# docker-testapp

This project is a Dockerized Node.js application that runs together with MongoDB and Mongo Express. Docker is used to containerize the application, Docker Compose is used to run multiple containers together, and Docker Volumes are used to persist MongoDB data so that data is not lost when containers are stopped or removed.

The tech stack used in this project includes Node.js for the backend application, MongoDB as the database, Mongo Express as a web-based MongoDB UI, Docker for containerization, Docker Compose for orchestration, and Docker Volumes for persistent storage.

The project structure is as follows:

testapp/
Dockerfile  
mongo.yaml  
server.js  
package.json  
package-lock.json  
node_modules/  
public/  
README.md

The Dockerfile uses a Node.js base image, copies the application source code into the container, installs the required dependencies, exposes port 5050, and starts the Node.js server.

The Docker Compose file used in this project is named mongo.yaml. It defines three services. The app service runs the Node.js application and exposes it on port 5050. The mongo service runs MongoDB and uses a Docker volume to persist database data. The mongo-express service runs Mongo Express and exposes it on port 8081 to provide a web interface for managing MongoDB. A Docker volume is attached to MongoDB so that data remains available even after containers are restarted.

To run the entire application stack using Docker Compose, use the following command (the file name must be specified explicitly because it is mongo.yaml):

docker compose -f mongo.yaml up -d

After the containers start successfully, the Node.js application can be accessed at:
http://localhost:5050

Mongo Express can be accessed at:
http://localhost:8081

When the Mongo Express login page opens, use the following credentials:
Username: admin  
Password: pass

::contentReference[oaicite:0]{index=0}

To stop and remove the containers created by Docker Compose, run:

docker compose -f mongo.yaml down

Alternatively, the application can be run directly using the Docker image published to Docker Hub without using Docker Compose.

To pull and run the Docker image:

docker pull tharunm490/testapp:2.0  
docker run -p 5050:5050 tharunm490/testapp:2.0

After running the container, the application can be accessed at:
http://localhost:5050

The Docker Hub image used in this project is:
tharunm490/testapp:2.0

Docker Compose is used only for orchestration, while the Docker image is reusable and can be pulled and run independently. MongoDB data persistence is handled using Docker volumes.
