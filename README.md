Node.js Hello World CICD Project
Overview
This project demonstrates a simple CI/CD pipeline setup for a Node.js "Hello World" application. The pipeline is configured to fetch the source code from GitHub, build a Docker image, and push the image to Docker Hub. Additionally, the project includes integration with Jenkins for continuous integration and SonarQube for code quality analysis.

Project Components
Jenkins: Automates the build process, including fetching code from GitHub, building the Docker image, and pushing it to Docker Hub.
SonarQube: Analyzes the code for quality, providing metrics and identifying potential issues.
Docker: Used for containerizing the application and distributing it.

URLs
Jenkins Server: http://172.174.175.86:8080/
username - mukul ; password - dynamics
SonarQube Dashboard: http://172.174.175.86:9000/
username - admin ; password - dynamics

CI/CD Pipeline
The CI/CD pipeline is defined in the Jenkinsfile located in the root of this repository. The pipeline includes the following stages:

Clone Repository: Pulls the latest code from the GitHub repository.
Build Docker Image: Builds a Docker image for the Node.js application.
Code Quality Analysis: Uses SonarQube to analyze the code.
Push Docker Image: Pushes the Docker image to Docker Hub under the repository optimusmukul/nodejs-hello-world.

Triggering the Build
To trigger the build manually, navigate to the Jenkins dashboard, select the nodejs_pipeline job, and click on Build Now. The pipeline will automatically execute the defined stages.

Pulling the Docker Image
To run the application locally, you can pull the Docker image from Docker Hub using the following command:

docker pull optimusmukul/nodejs-hello-world

Running the Docker Container
After pulling the image, you can run the container locally with:

docker run -p 3000:3000 optimusmukul/nodejs-hello-world

This command will start the application and make it accessible at http://localhost:3000.
