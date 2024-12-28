# Three-Tier CI/CD Pipeline

This repository contains a Jenkins pipeline for a simple three-tier architecture setup involving a **Back-end**, **Front-end**, and **Database**. The pipeline is designed to be used with Docker images for Maven, Node.js, and MySQL to build, test, and deploy components in an isolated environment.

## Pipeline Structure

The pipeline consists of three main stages:

### 1. **Back-end** 
   - **Technology**: Java (Maven)
   - **Purpose**: This stage installs and builds the back-end using Maven.
   - **Docker Image**: `maven:3.8.1-adoptopenjdk-11`
   - **Steps**:
     - Runs `mvn clean install` to build the back-end application.

### 2. **Front-end** 
   - **Technology**: Node.js (React or similar)
   - **Purpose**: This stage installs dependencies and builds the front-end.
   - **Docker Image**: `node:16-alpine`
   - **Steps**:
     - Runs `npm install` to install dependencies.
     - Runs `npm run build` to build the front-end application.

### 3. **Database** 
   - **Technology**: MySQL
   - **Purpose**: This stage checks the MySQL version and runs a basic query to show tables.
   - **Docker Image**: `mysql:latest`
   - **Steps**:
     - Runs `mysql --version` to check the MySQL version.
     - Executes a simple query to show the available tables.

## Prerequisites

Before running the pipeline, ensure the following:

1. **Jenkins** is installed and configured with the required plugins (such as Docker).
2. **Docker** is installed and running on the Jenkins agent.
3. Docker images used in the pipeline are available:
   - `maven:3.8.1-adoptopenjdk-11`
   - `node:16-alpine`
   - `mysql:latest`

## Running the Pipeline

1. Clone this repository to your Jenkins environment.
2. Configure a Jenkins job with this pipeline script.
3. Trigger the job to run the pipeline stages for back-end, front-end, and database.

## Notes

- The pipeline assumes basic familiarity with Jenkins and Docker.
- Modify the pipeline stages according to your project's specific build and deployment requirements.
- The database stage is a simple example; you can expand this to include database migration or testing steps.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
