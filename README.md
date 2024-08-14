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
