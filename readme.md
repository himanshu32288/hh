# Project Title

MongoDB Instance on Docker

## Group Members

- Himanshu Kumar, Roll No. 2K19/CO/159
- Prince Sharma, Roll No. 2K19/CO/299
- Purshottam Kumar, Roll No. 2K19/CO/300

## Description

This project involves creating a MongoDB instance on Docker, creating a database with sample data, and performing some basic operations on the data. The project was completed by following these steps:

1. Install Docker from [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)
2. Pull the MongoDB image using the command `docker pull mongo`
3. Create a MongoDB container using the command `docker run --name <container-name> -d mongo:latest`
4. Start the container using the command `docker exec -it <container-name> bash`
5. Create a database in the MongoDB container and insert three records using the following commands:

db..insert({name : "Purshottam Kumar", position : "Manager"})
db..insert({name : "Prince Sharma", position : "sde"})
db._.insert({name : "Himanshu Kumar", position : "Manager"}) 

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
