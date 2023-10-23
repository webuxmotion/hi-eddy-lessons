---
sidebar_position: 2
---

# Creating a Dockerfile

## Build image and run container for production

Create file:
```bash title="Dockerfile"
FROM node:alpine
WORKDIR /usr/src/app
COPY ./package.json .
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "run", "start"]
```

Run commands:
```bash
# Build image
docker build -t nodeapp .

# Run container
docker run --name my-node-app -p 8000:3001 -v $(pwd):/usr/src/app -v /usr/src/app/node_modules nodeapp
```

## Build image and run container for development

Create file:
```bash title="Dockerfile.dev"
FROM node:alpine
WORKDIR /usr/src/app
COPY ./package.json .
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "run", "start:dev"]
```

Run commands:
```bash
# Build image
docker build -t nodeapp:v2 -f Dockerfile.dev .

# Run container for development
docker run --name my-node-app-dev -p 8001:3001 -v $(pwd):/usr/src/app -v /usr/src/app/node_modules nodeapp:v2
```