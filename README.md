# DevOps – Docker Nginx Project

## 📌 Project Description
This project demonstrates building a Docker image based on Ubuntu,
installing and running an Nginx web server, and serving a simple HTML page.

The project also shows:
- Working with Git branches and Pull Requests
- Port mapping (host → container)
- Using Docker Volumes for persistent data

---

## 🧱 Project Structure
DevOps/
│── Dockerfile
│── index.html
│── README.md
│── site/
│ └── index.html

yaml
Copy code

---

## ⚙️ Dockerfile Explanation
- `FROM ubuntu:22.04` → Base Linux image  
- `RUN apt-get update && apt-get install -y nginx` → Install Nginx  
- `WORKDIR /var/www/html` → Web root directory  
- `COPY index.html .` → Copy website file into container  
- `EXPOSE 80` → Expose web port  
- `CMD ["nginx", "-g", "daemon off;"]` → Run Nginx in foreground  

---

## 🚀 Run Without Volume
```bash
docker build -t myapp:1 .
docker run -d --name myapp -p 8080:80 myapp:1
docker ps
