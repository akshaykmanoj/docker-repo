# Repository for Learning Containerization - Docker
# This repository is created for learning and understanding containerization using Docker.

# prerequisites
- Learn basics of CI/CD , Jenkins , Docker , DockerImages etc.
- Learn Dockerfile components: [FROM, EXPOSE, RUN, ADD, MAINTAINER, ENTRYPOINT, CMD, ENV, COPY, WORKDIR]
- Learn Docker commands: [list image, build image, remove image, run container, list running containers, stop/kill running container, remove all images, login, logout]

# Repository Contents

  Java Maven Code: This repository contains a sample Java Maven code that can be used as a starting point for building your own applications using Docker.
Dockerfile: The Dockerfile provided in this repository serves as a blueprint for building a Docker image. It includes the necessary instructions to package the Java Maven code into a containerized application.(according to my learning objective)
Jenkins Pipeline Script: a Jenkins pipeline script that automates the build, test, and deployment process. it performs actions such as code checkout, Maven build, unit testing, code analysis, Docker login, image building, tagging, and pushing to a Docker registry.
# To get started with learning containerization using Docker and utilizing this repository, follow the steps below:

  Install Docker on your EC2 instance: Ensure that Docker is properly installed on your EC2 instance. This will allow you to run and manage containers.
Create an account on DockerHub: Sign up for an account on DockerHub, which is a popular container registry. This will enable you to push Docker images to a central repository for sharing.
Set up Jenkins Pipeline: Configure Jenkins and create a new pipeline job. The Jenkins pipeline script provided in this repository can be used as a starting point. Customize it as per your requirements and configure any necessary credentials for Docker login.
Execute the Pipeline: Run the Jenkins pipeline job to trigger the build process. The pipeline script will perform the following tasks:
    Check out the code from the repository
    Build the Maven code
    Execute unit tests
    Perform code analysis
    Log in to DockerHub
    Build the Docker image
    Tag the image with the build number
    Push the image to DockerHub
    Log out from DockerHub
# Contributing

Contributions to this repository are welcome. If you have any improvements, bug fixes, or additional features, feel free to open a pull request. Please ensure that your contributions align with the purpose of the repository and follow best practices for Docker, Jenkins, and containerization.

# Contact

If you have any questions, suggestions, or feedback, please feel free to contact @ akshaykmanoj45@gmail.com . I appreciate your interest and involvement in learning containerization with Docker.
