#  Containerized Django Application Deployment on AWS EC2

This project demonstrates how to containerize a Django web application using Docker and deploy it on an AWS EC2 instance.

---

##  Tech Stack

- Python (Django)
- Docker
- AWS EC2
- Linux
- Docker Hub

---


##  Features

- Dockerized Django application
- Port mapping and container networking
- AWS Security Group configuration
- Publicly accessible deployment
- Docker Hub image push

---

##  Docker Image

Docker Hub Repository:
https://hub.docker.com/r/omshresth10/django-app

---

##   Deployment Steps
- Clone the Repository
git clone https://github.com/omshresth/django-docker-aws-deployment.git
cd django-docker-aws-deployment
- Build Docker Image
docker build -t omshresth10/django-app:latest .
- Run Docker Container
docker run -d -p 8000:8000 omshresth10/django-app:latest
- Configure AWS Security Group
Ensure EC2 inbound rules allow:
-SSH → Port 22
-Custom TCP → Port 8000
- Access the Application
http://<EC2-PUBLIC-IP>:8000

##  Key Learnings

-Docker image lifecycle (build, tag, push, run)
-Container networking and port mapping
-Cloud security group configuration
-Public deployment workflow
-Difference between development and production server

⚠️ Important Note

This deployment uses Django’s development server (runserver).

-For production environments, it is recommended to use:
-Gunicorn (WSGI server)
-Nginx (Reverse Proxy)
-HTTPS (SSL certificate)
-DEBUG = False
-Environment variables for SECRET_KEY

🔜 Future Improvements

-Integrate Gunicorn
-Add Nginx reverse proxy
-Implement HTTPS
-Setup CI/CD pipeline
-Deploy using Docker Compose
-Use PostgreSQL instead of SQLite
