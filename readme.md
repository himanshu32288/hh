# Project Title
Docker container for MYSQL and MongoDb instance.
## Links
Mongodb: https://hub.docker.com/r/himanshusahani20/mongo-db/tags \
MYSQL:  https://hub.docker.com/r/himanshusahani20/my-mysql-image/tags 

## Group Members

- Himanshu Kumar, Roll No. 2K19/CO/159
- Prince Sharma, Roll No. 2K19/CO/299
- Purshottam Kumar, Roll No. 2K19/CO/300

## Description

1. Install Docker from [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)
2. Pull the MongoDB image using the command `docker pull mongo`
3. Create a MongoDB container using the command `docker run --name <container-name> -d mongo:latest`
4. Start the container using the command `docker exec -it <container-name> bash`
5. Create a database in the MongoDB container and insert three records using the following commands:
```
db..insert({name : "Purshottam Kumar", position : "Manager"})
db..insert({name : "Prince Sharma", position : "sde"})
db._.insert({name : "Himanshu Kumar", position : "Manager"})
```
6. Update the position of one record from "Manager" to "sde" using the following command:

db.empl.updateOne({name: "kartik"}, [{$set: {position: "sde"}}])

7. Remove the name of one record using the following command:

db.empl.remove({Name: "himanshu"})

8. Sign up for Docker and push the data to our Docker repository using the command `docker push <repository-name>`
9. Get the DockerHub link on our profile at [https://hub.docker.com/r/himanshusahani20/mongo-db/tags](https://hub.docker.com/r/himanshusahani20/mongo-db/tags)

## Commands Used

- `docker pull mongo`: Pulls the MongoDB image
- `docker run --name <container-name> -d mongo:latest`: Creates a MongoDB container
- `docker exec -it <container-name> bash`: Starts the MongoDB container
- `db._.insert({name : "<name>", position : "<position>"})`: Inserts a record in the database
- `db.empl.updateOne({name: "<name>"}, [{$set: {position: "<new-position>"}}])`: Updates a record in the database
- `db.empl.remove({Name: "<name>"})`: Removes a record from the database

## DockerHub Repository Link

[https://hub.docker.com/r/himanshusahani20/mongo-db/tags](https://hub.docker.com/r/himanshusahani20/mongo-db/tags)  
## Steps
1. Create a Dockerfile to define the MySQL image. In a text editor, create a new file named `Dockerfile` (without an extension) with the following contents. 
### Dockerfile
```
FROM mysql:latest
ENV MYSQL_ROOT_PASSWORD mypassword
COPY init.sql /docker-entrypoint-initdb.d/ 
```
2. Created the initialization script. In the same directory as the Dockerfile, created a new file named init.sql with the following contents:
CREATE DATABASE example;
```
CREATE DATABASE bdadatabase;
USE bdadatabase;
CREATE TABLE group (id INT, name VARCHAR(255), email VARCHAR(255));
INSERT INTO group VALUES (1, 'Prince Sharma', 'princeurfrajaji@gmail.com');
INSERT INTO group VALUES (2, 'Himanshu Kumar', 'kyahibolu@gmail.com');
INSERT INTO group VALUES (3, 'Purshottam Kumar', 'handsomeboy@gmail.com');
```
3. Build the Docker image. Open a terminal or command prompt, navigate to the directory containing the Dockerfile and init.sql files, and run the following command: \
    `docker build -t my-mysql-image .`
4. Run the Docker container. Once the image has been built, you can run it using the following command: \
    `docker run -d -p 3306:3306 --name my-mysql-container my-mysql-image`
5. Finally, pushed the image to Docker Hub: 
   docker push himanshusahani20/my-mysql-image 
6.Get the DockerHub link on our profile at https://hub.docker.com/r/himanshusahani20/my-mysql-image/tags
