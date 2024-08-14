# Node.js Hello World Application

This is a simple Node.js application that displays "Hello World". The application has been dockerized for easy deployment.

## Prerequisites

- **Docker**: Make sure Docker is installed on your machine. You can download Docker from [Docker's official website](https://www.docker.com/get-started).

## Getting Started

- **Initialize a New Node.js Project:**
  
  Open a terminal and create a new directory for your project. Then, initialize a new Node.js project using npm:

```
mkdir hello-world-app
cd hello-world-app
npm init -y
```
- **Install Express:**
  
  Install the Express framework, which will help you set up a simple server:

```
npm install express
```
- **Create the Application File:**

  Create a new file named app.js and add the following code:

```
const express = require('express');
const app = express();
const port = 3000;

app.get('/', (req, res) => {
  res.send('Hello, World!');
});

app.listen(port, () => {
  console.log(`Server running at http://localhost:${port}/`);
});
```
- **Run the Application:**

  Add a start script to your package.json file. Open package.json and modify the "scripts" section to include:

```
"scripts": {
  "start": "node app.js"
}
```
- **Run Application:**
    Run and test the application using:

  ```
  npm start
  ```

## Dockerize Node.js application
  
  - **Write Dockerfile:**

    In your project directory, create a file named Dockerfile with the following content:

    ```
    
    FROM node:18
    
    WORKDIR /app
    
    COPY . .
    
    RUN npm install
    
    EXPOSE 3000
    
    CMD ["npm", "start"]
    ```
      
   - **Build the Docker Image:**
    
     In your project directory, build the Docker image using the following command:
        
       ```
        docker build -t hello-world-app .
      ```
    
  - **Run the Docker Container:**
        
    Once the image is built, run a container using the following command:
  
      ```
        docker run -p 3000:3000 hello-world-app
      ```
    
   - **Access the Application:**

     Open a web browser and navigate to http://localhost:3000. You should see "Hello, World!" displayed, just as you did before Dockerizing the application.

     
   - **Push the image:**

      Login in DockerHub through terminal:
      
      ```
      docker login
      ```
     Tag the image using:

     ```
     docker tag <local_image_name>:<version_of_local_image> \ <new_image_name>:<new_version>
     ```
     
     Finally, push the image:

      ```
      docker push<user_name>/<new_image_name>:<new_version>
      ```


    

