# 🚀 docker-testapp

<p align="center">
	<b>A Dockerized Node.js, MongoDB, and Mongo Express stack</b>
</p>

---

---

## 📝 Project Overview

This project is a Dockerized Node.js application that runs together with MongoDB and Mongo Express. It uses:

- **Node.js** for the backend
- **MongoDB** as the database
- **Mongo Express** as a web-based MongoDB UI
- **Docker** for containerization
- **Docker Compose** for orchestration
- **Docker Volumes** for persistent storage

---

## 📁 Project Structure

```text
testapp/
├── Dockerfile
├── mongo.yaml
├── server.js
├── package.json
├── public/
│   ├── index.html
│   └── style.css
└── README.md
```

---

## ⚙️ Usage

### 1. Build & Run with Docker Compose

```sh
docker compose -f mongo.yaml up -d
```

### 2. Access the Application

- Node.js app: [http://localhost:5050](http://localhost:5050)
- Mongo Express: [http://localhost:8081](http://localhost:8081)

**Mongo Express Credentials:**

| Username | Password |
| -------- | -------- |
| admin    | pass     |

### 3. Stop & Remove Containers

```sh
docker compose -f mongo.yaml down
```

---

## 🐳 Run from Docker Hub

```sh
docker pull tharunm490/testapp:2.0
docker run -p 5050:5050 tharunm490/testapp:2.0
```

App will be available at [http://localhost:5050](http://localhost:5050)

---

## 📦 Docker Images

- Docker Hub: `tharunm490/testapp:2.0`

---

## 💾 Data Persistence

MongoDB data is persisted using Docker volumes, so your data is safe even if containers are stopped or removed.

---

## 📚 License

MIT

docker compose -f mongo.yaml down

Alternatively, the application can be run directly using the Docker image published to Docker Hub without using Docker Compose.

To pull and run the Docker image:

docker pull tharunm490/testapp:2.0  
docker run -p 5050:5050 tharunm490/testapp:2.0

After running the container, the application can be accessed at:
http://localhost:5050

The Docker Hub image used in this project is:
tharunm490/testapp:2.0

Docker Compose is used only for orchestration, while the Docker image is reusable and can be pulled and run independently. MongoDB data persistence is handled using Docker volumes.
