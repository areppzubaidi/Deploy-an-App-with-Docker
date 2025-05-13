# 🚀 Deploy a Containerized Web App with Docker & AWS Elastic Beanstalk

_A hands-on project demonstrating how to containerize a web application using Docker and deploy it to AWS Elastic Beanstalk._

---

## 📌 Project Overview

### 🎯 Objective

Learn containerization fundamentals by:

- Creating a custom Docker image  
- Running containers locally  
- Deploying to AWS Elastic Beanstalk  
- Updating the live application  

---

## 🛠 Key Technologies

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
  ```
- Ran first container using Nginx:
  ```bash
  docker run -d -p 8080:80 nginx
  ```

### 2. Custom Image Creation
- Created a `Dockerfile`:
  ```Dockerfile
  FROM nginx:latest
  COPY index.html /usr/share/nginx/html/
  EXPOSE 80
  ```
- Built the custom image:
  ```bash
  docker build -t my-web-app .
  ```

### 3. Local Deployment
- Ran the container locally:
  ```bash
  docker run -d -p 80:80 my-web-app
  ```
- Verified output at: [http://localhost](http://localhost)

---

## ☁️ AWS Elastic Beanstalk Deployment

- Created an Elastic Beanstalk application  
- Selected **Docker** platform  
- Zipped and uploaded project files  

**Environment Configuration:**
- Single instance (Free Tier)  
- Public IP enabled  
- gp3 root volume  

---

## 🔁 Application Update

- Modified `index.html`  
- Created a new ZIP package  
- Re-deployed using Elastic Beanstalk Console  

---

## 📸 Screenshots

- ✅ Local Container  
- ✅ Elastic Beanstalk Deployment  

---

## 🎯 Key Learnings

- ✅ **Containerization Benefits:** Solved the “works on my machine” problem  
- ✅ **Docker Workflow:** Build → Run → Deploy cycle  
- ✅ **AWS Integration:** Simplified deployment with Elastic Beanstalk  
- ✅ **CI/CD Concepts:** Introduction to zero-downtime deployment  

---

## 🧹 Cleanup

Be sure to:

```bash
docker container prune
docker image prune
```

Also:
- Terminate the Elastic Beanstalk environment  
- Delete the S3 bucket created during deployment  

---

## 🚀 Further Improvements

- 🔁 Add a CI/CD pipeline with GitHub Actions  
- 🟢 Implement blue/green deployments  
- 🩺 Add health checks and monitoring  
- 🧩 Scale to a multi-container architecture using Docker Compose or ECS
