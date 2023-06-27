# Python Flask ile Basit MongoDB Crud İşlemleri

## Creating Network for Containers

```
docker network create mongo-flask
```

## Creating Container for Mongo
Data will be write in data folder

```
docker run -d --name mongodb --network=mongo-flask -p 27017:27017 -v localpath\data:/data/db -e MONGO_INITDB_DATABASE=Users mongo:latest
```
## Creating Container for Flask

```
docker build -t my-flask-app .

docker run -d --name flaskapp --network=mongo-flask -p 5000:5000  my-flask-app
```