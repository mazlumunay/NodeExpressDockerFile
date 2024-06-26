Assignment 3
Lambton College
FSDT - Full Stack Software Development
DevOps - Tools and Practices
Objective
Deploy a Node.js application as a Docker container using a Dockerfile.
Steps
Create a Node.js + Express Application
Develop an application with index.html and five API endpoints.
Create a GitHub Repository
Sign in to GitHub and create a new repository.
Push the application code to the repository.
Create a Dockerfile
Write a Dockerfile to define the Docker image for the application.
Build the Docker Image
Use the Dockerfile to create a Docker image.
Push the Docker Image to Docker Hub
Push the newly created Docker image to Docker Hub.
Install the Application Dependencies
Run npm install to install the necessary dependencies.
Run the Application
Start the application using npm start.
Commands
To push the code to GitHub, use the following commands in the terminal:
bash
git add .
git commit -m "feat: create node express app"
git push

Example Dockerfile
dockerfile
FROM node:10-alpine

RUN mkdir -p /home/node/app/node_modules && chown -R node:node /home/node/app

WORKDIR /home/node/app

COPY package*.json ./

USER node

RUN npm install

COPY . .

EXPOSE 8080

CMD [ "node", "app.js" ]

Example .dockerignore
plaintext
node_modules
npm-debug.log
Dockerfile
.dockerignore

Building and Running the Docker Image
Build the Docker Image:
bash
docker build -t your_dockerhub_username/nodejs-image-demo .

Push the Docker Image to Docker Hub:
bash
docker push your_dockerhub_username/nodejs-image-demo

Run the Docker Container:
bash
docker run -p 8080:8080 your_dockerhub_username/nodejs-image-demo

By following these steps, you will successfully deploy your Node.js application as a Docker container.
