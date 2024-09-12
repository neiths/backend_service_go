# backend_service_go

1. Design database schema using DBML and automatically generate SQL code from it

website to design database: `https://dbdiagram.io`

![alt text](assets/schema_db.png)

install golang/migrate `https://github.com/golang-migrate/migrate/tree/master/cmd/migrate`

for Quickinstall

```
$ curl -s https://packagecloud.io/install/repositories/golang-migrate/migrate/script.deb.sh | sudo bash
$ apt-get update
$ apt-get install -y migrate
```

start postgres db through docker

``` 
docker run --name postgres16 -p 5433:5432 -e POSTGRES_USER=root -e POSTGRES_PASSWORD=secret -d postgres:16-alpine

# through terminal shell
docker exec -it postgres16 /bin/bash
createdb --username=root --owner=root simple_bank
dropdb simple_bank

docker exec -it postgres16 createdb --username=root --owner=root simple_bank

docker exec -it postgres16 psql -U root simple_bank
```
migrate -path db/migration -database "postgresql://root:secret@localhost:5433/simple_bank?sslmode=disable" -verbose up



golang migrat: `https://github.com/golang-migrate/migrate`

2. Deeply understand the DB isolation levels, transactions and how to avoid deadlock
3. Automatically generate Golang code to interact with the database
4. Develop a RESTful backend web service using the Gin framework
5. Secure the APIs with user authentication, JWT and PASETO
6. Write stronger test set with high coverage using interfaces and mocking
7. Build a minimal Docker image for deployment and use Docker-compose for development
8. Set up Github Action to automatically build and deploy the app to AWS Kubernetes cluster
9. Register a domain and config Kubernetes ingress to route traffic to the web service
10. Enable automatic issue & renew TLS certificate for the domain with Let's Encrypt
11. Take your web service to the next level with gRPC and gRPC gateway
12. Run background workers to process tasks asynchronously with Redis and Asynq
