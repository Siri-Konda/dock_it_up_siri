Assignment 1 — Build & Run a Personalized Web Server Container

## Overview

As required by the assignment, this project demonstrates 
The goal is to show:
* **creating a container** 
* **running** the container using **custom ports**

---
## Video link

Here is a video of the website running: 
https://drive.google.com/file/d/1690u2M85QDTmtQMTYVKcRrjHkjegJCK4/view?usp=drive_link

## Project Structure

```
assignment-1/
├── Dockerfile
├── index.html
├── me.html
├── surprise.html
├── web.html
└── README.md
```

---


## Setup & Execution Steps

### 1. Build Web Image
(Here, we are trying to build an image with the **tag** (-t), aka name about-duck.)

Run this inside the project directory:

```bash
docker build -t about-duck .
```
---

### 2. Run Container
(-d is used to run the container in the background, site1 is the name of the container (usually a container is stored as a sequence of numbers and letters, eg. 23454944e86e402eb4b39ce0d619e58be4ead7eaef1d8ce63ef745ea25d06587). 9090:8000 is the port we connect to.)

Run this: 

```bash
docker run -d --name site1 -p 9090:8000 about-duck
```

---

### 3. Browser Test (optional)

Open your browser and go to:

```
http://localhost:9090
```
**DO NOT OPEN THE SITE USING CLI** AS THERE ARE SOME SURPRISES HIDDEN IN THE WEBPAGE
---

### 4. Cleanup (Optional)

To stop and remove containers:

```bash
docker stop site1
docker rm site1
```

---


