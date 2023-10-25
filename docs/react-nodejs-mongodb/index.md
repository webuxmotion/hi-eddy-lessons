---
sidebar_position: 10
---

# Run ReactJS_NODEJS_MongoDB application in one network

## Clone project and go to project folder
```bash
git clone https://github.com/webuxmotion/react-nodejs-mongodb
cd react-nodejs-mongodb
```

## Create network
```bash
docker network create todo-net
```

## Run mongodb container
```bash
docker run --name mongodb --network todo-net -d --rm -p 27017:27017 -v mongodb-data:/data/db mongo
```

## Build backend image and run backend-todo container
```bash
cd backend
docker build -t backend .
docker run --name backend-todo --network todo-net -d --rm -p 8000:8000 -v $(pwd)/src:/app/src backend
```

## Build frontend image and run frontend-todo container
```bash
cd ../frontend
docker build -t frontend .
docker run --name react-todo -d --rm -it -p 3001:3000 -v $(pwd)/src:/app/src frontend
```

## Open site in browser
[http://localhost:3001](http://localhost:3001)