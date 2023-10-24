---
sidebar_position: 0
---

# ReactJS + NODEJS + MongoDB

## Clone project
```bash
git clone https://github.com/webuxmotion/react-nodejs-mongodb
cd react-nodejs-mongodb

docker run --name mongodb -d --rm -p 27017:27017 mongo
```

```bash title="/backend/Dockerfile"
FROM node:alpine

WORKDIR /app

COPY package.json

RUN npm install

COPY . .

EXPOSE 8000

CMD ["npm", "run", "start"]
```

```bash
cd backend
docker build -t todoapp .
docker run --name todo-app --rm todoapp
```

Mongo URL for connection:

"mongodb://host.docker.internal:27017/toods-app"
