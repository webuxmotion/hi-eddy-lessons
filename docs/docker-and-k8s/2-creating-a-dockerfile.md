---
sidebar_position: 2
---

# Creating a Dockerfile

```txt title="Dockerfile"
FROM node:alpine
WORKDIR /usr/src/app
COPY . .
RUN npm install
EXPOSE 3001
CMD ["npm", "run", "start"]
```

```bash
docker build -t nodeapp .
docker images
docker run --name my-node-app -p 8000:3001 nodeapp
docker ps
```