
# Assignment 2 — Create & Run Two Containers That Communicate

## Overview

As required by the assignment, this project demonstrates **container-to-container communication using Docker**. A **web container (Nginx)** serves static HTML pages and communicates with an **API container** over a **custom Docker network** using container names.

The goal is to show:

* Use of a **custom Docker network**
* Running two containers — one static web server and one simple API 
* Connect them using Docker networking

---

## Project Structure

```
assignment-2/
├── Dockerfile
├── index.html
├── api.html
├── default.conf
└── README.md
```

---


## Setup & Execution Steps

### 1. Create Docker Network

```bash
docker network create webnet
```
---

### 2. Build the Web Image

Run this inside the project directory:

```bash
docker build -t web-image .
```

---

### 3. Run the API Container

```bash
docker run -d --name api --network webnet hashicorp/http-echo -text="Hello from API"
```

---

### 4. Run the Web Container

```bash
docker run -d --name web --network webnet -p 8080:80 web-image
```

### 5. Test that the web container can reach the API container using container name:

Run this code:  

```bash
docker exec -it web curl http://api:5678
```

Expected Output:

```
Hello from API
```

---

### 6. Browser Test (optional)

Open your browser and go to:

```
http://localhost:8080
```

Click the **Call API** button to see the API response.

---

### 7. Cleanup (Optional)

To stop and remove containers:

```bash
docker stop web 
docker stop api
docker rm web 
docker rm api
```

To remove the network:

```bash
docker network rm webnet
```

---

