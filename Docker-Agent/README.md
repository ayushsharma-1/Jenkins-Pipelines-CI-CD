# Jenkins Pipeline with Dockerized Node.js

This repository contains a Jenkins pipeline script that runs Node.js commands within a Docker container. It is designed to test the environment setup by verifying the Node.js version and installing dependencies in a clean, reproducible environment.

---

## Features

- **Docker Integration**: Utilizes the `node:18-alpine` Docker image for a lightweight Node.js environment.
- **Multi-Stage Pipeline**: Includes separate stages for:
  - Checking the Node.js version.
  - Installing dependencies using `npm install`.
- **Flexible Agent Configuration**: Allows the use of labeled Jenkins agents for better resource allocation.
- **Post-Execution Actions**: Ensures a clean log and potential follow-up actions upon pipeline completion.

---

## Requirements

- **Jenkins**: Version 2.0+ with Docker support enabled.
- **Docker**: Ensure Docker is installed and running on the Jenkins agent.
- **Node.js Project**: A project with an `npm`-compatible `package.json` file.

---
