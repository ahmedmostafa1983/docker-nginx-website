# Website Deployment Using Nginx, Dockerfile, and Docker Hub

##  Project Overview

This project demonstrates how to deploy a **simple website** using **Nginx** by building a custom Docker image with a **Dockerfile**, then pushing the image to **Docker Hub** and running containers from it.

The project covers the full container lifecycle:

* Build
* Run
* Commit
* Push
* Pull

---

##  Technologies Used

* Nginx
* Docker
* Docker Hub

---

##  Website Path

The website files are located at:

```
/Course-Docker/sample-website
```

---

##  Dockerfile

```dockerfile
FROM nginx:latest
COPY ./Course-Docker/sample-website /usr/share/nginx/html/
EXPOSE 80
```

---

##  How to Run the Project

###  1-Clone the repository

```bash
git clone https://github.com/MenaMagdyHalem/Course-Docker.git
cd Course-Docker
```

---

### 2- Build the Docker image

```bash
docker build -t website .
```

---

### 3- Run the container

```bash
docker run -d -p 3000:80 --name web website
```

Access the website:

```
http://localhost:3000
```

---

##  Commit the Running Container

```bash
docker commit web menamagdyhalem/new-web
```

---

##  Login to Docker Hub

```bash
docker login
```

---

##  Push Image to Docker Hub

```bash
docker push menamagdyhalem/new-web
```

The image is now available on Docker Hub.

---

##  Pull and Run Image from Docker Hub

```bash
docker run -d -p 4000:80 --name new-hub menamagdyhalem/new-web
```

Access the website:

```
http://localhost:4000
```

---

##  Key Learning Outcomes

* Writing Dockerfiles
* Building Docker images
* Running containers with port mapping
* Using `docker commit`
* Pushing and pulling images from Docker Hub
* Understanding container image distribution

---

## 👨‍💻 Author

Ahmed Mostafa
