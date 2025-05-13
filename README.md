# 🚀 Deploy a Containerized Web App with Docker & AWS Elastic Beanstalk

![Project Banner](https://storage.googleapis.com/nextwork_course_resources/courses/aws/AWS%20Project%20People%20projects/Project%3A%20Containers%20on%20Elastic%20Beanstalk/NextWork%20Course%20Trophy%20Badge.png)

A hands-on project demonstrating how to containerize a web application using Docker and deploy it to AWS Elastic Beanstalk.

---

## 📌 Project Overview

**🎯 Objective**  
Learn containerization fundamentals by:

1. Creating a custom Docker image  
2. Running containers locally  
3. Deploying to AWS Elastic Beanstalk  
4. Updating the live application

**🛠 Key Technologies**
- 🐳 Docker
- ☁️ AWS Elastic Beanstalk
- 🖥️ Nginx web server
- 📦 Containerization concepts

---

## 🛠️ Implementation Steps

### 1. Docker Setup
- Installed Docker Desktop
- Verified installation with:
  ```bash
  docker --version
Ran first container using Nginx:

bash
Copy
Edit
docker run -d -p 8080:80 nginx
2. Custom Image Creation
Created a Dockerfile:

dockerfile
Copy
Edit
FROM nginx:latest
COPY index.html /usr/share/nginx/html/
EXPOSE 80
Built custom image:

bash
Copy
Edit
docker build -t my-web-app .
3. Local Deployment
Ran the container locally:

bash
Copy
Edit
docker run -d -p 80:80 my-web-app
Verified output at: http://localhost

4. AWS Elastic Beanstalk Deployment
Created an Elastic Beanstalk application

Selected Docker platform

Zipped and uploaded project files

Environment configuration:

Single instance (Free Tier)

Public IP enabled

gp3 root volume

5. Application Update
Modified index.html

Created a new ZIP package

Re-deployed using Elastic Beanstalk console

📸 Screenshots
Local Container	Elastic Beanstalk Deployment

🎯 Key Learnings
✅ Containerization Benefits: Solved the “works on my machine” problem
✅ Docker Workflow: Build → Run → Deploy cycle
✅ AWS Integration: Simplified deployment with Elastic Beanstalk
✅ CI/CD Concepts: Introduction to zero-downtime deployment

🧹 Cleanup
Be sure to:

Terminate the Elastic Beanstalk environment

Delete the S3 bucket created during deployment

Remove local Docker containers/images:

bash
Copy
Edit
docker container prune
docker image prune
🚀 Further Improvements
🔁 Add a CI/CD pipeline with GitHub Actions

🟢 Implement blue/green deployments

🩺 Add health checks and monitoring

🧩 Scale to a multi-container architecture using Docker Compose or ECS
