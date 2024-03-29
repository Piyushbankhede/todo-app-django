# Django ToDo App with Jenkins Pipeline and Docker Deployment on AWS

## Introduction

This repository contains a simple ToDo web application built using Django. Additionally, it includes a Jenkins pipeline for continuous integration and deployment. The application is containerized using Docker, and the deployment is orchestrated on AWS.

## Features

- Django-based ToDo web application.
- Jenkins pipeline for automated build and deployment.
- Docker containerization for easy deployment.
- AWS integration for hosting the Docker container.

## Prerequisites

Before getting started, make sure you have the following installed:

- Python (3.x recommended)
- Docker
- Jenkins
- AWS account with configured access credentials

## Getting Started

1. **Clone the Repository:**

    ```bash
    git clone https://github.com/Piyushbankhede/todo-app-django.git
    cd todo-app
    ```

2. **Set Up Django Environment:**

    ```bash
    pip install -r requirements.txt
    python manage.py migrate
    python manage.py runserver
    ```

    Visit http://localhost:8000 in your browser to ensure the app is working locally.

3. **Jenkins Setup:**

    - Install Jenkins and set up a new pipeline job.
    - Configure the pipeline to pull from your GitHub repository.
    - Add the necessary Jenkinsfile provided in this repository.

4. **Docker Hub Integration:**

    - Create an account on [Docker Hub](https://hub.docker.com/).
    - Set up a new repository for your ToDo app.
    - Ensure your Jenkins pipeline is configured to push the Docker image to this repository.
    - To install todo-images (cantainer) [todo-app-images](https://hub.docker.com/repository/docker/piyushbankhede/todo-app/general)

5. **AWS Deployment:**

    - Set up an EC2 instance on AWS with Docker installed.
    - Configure the necessary security groups and IAM roles.
    - Update the AWS credentials in your Jenkins environment.

6. **Run Jenkins Pipeline:**

    - Trigger the Jenkins pipeline manually or set up a webhook for automatic builds.
    - The pipeline will build the Docker image, push it to Docker Hub, and deploy it on your AWS instance.
    

7. **Access the Deployed App:**

    Visit your AWS EC2 instance's public IP or domain to access the deployed ToDo app.


8. **some important configuration:**


    ![jenkins conf.](screenshot/Screenshot%202024-01-07%20012544.png) 

   - In this you have to paste your github (source code )link and configure it
 
    ![build trigger](screenshot/Screenshot%202024-01-07%20012557.png)

   - you have to enable a trigger to automate your pipeline so here we can use a  ->"Github Hook triggers GITScm polling " trigger
    
    ![github/todo](screenshot/Screenshot%202024-01-07%20013247.png)   
    
     - In github we have to configure a webook to connect to jenkins 

     ![github-webook](screenshot/Screenshot%202024-01-07%20013315.png) 
     
    - here we can create a webhook and assign it to jenkis

     ![todo-build toto-deploy](screenshot/Screenshot%202024-01-07%20012451.png) 

    - here our both build and deploy job are run 

     ![dockerhub-images](screenshot/Screenshot%202024-01-07%20013607.png)

     - Docker images recived by verion vise 

    ![final-app](screenshot/Screenshot%202024-01-12%20163210.png)
      

     

## Contributing

Feel free to contribute to the project by opening issues or submitting pull requests.



## License

This project is licensed under the [MIT License](LICENSE).
