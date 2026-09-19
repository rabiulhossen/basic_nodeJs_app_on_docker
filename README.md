## 🐳 Project: Node.js App → Docker Container

- #### Step 1 — Set up Node.js Project
npm init -y
npm i express

- #### Step 2 — Create Dockerfile

FROM node:22-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 3000

CMD ["node", "server.js"]

- #### Step 3 - Create .dockerignore

- #### Step 4 - Build a Image

docker build -t my-node-app .
- #### Step 5 - Run Container

docker run -d --name my-node-container -p 3000:3000 my-node-app

- #### Step 5 - Container check & logs
docker ps
docker logs my-node-container




