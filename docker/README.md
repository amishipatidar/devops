# Docker Homework Tasks

## Objective

The objective of this homework is to create and run simple Hello World web applications using Docker.

The following applications were created:

1. Node.js
2. Python
3. Java
4. Apache
5. React
6. Nginx

Each application has its own folder, application code, and Dockerfile. Docker images were built and containers were run to verify the applications through web browsers.

---

## 1. Node.js Application

### Folder

```text
docker/nodejs-app/
```

### Files

- `app.js`
- `Dockerfile`

### Docker Image

```bash
docker build -t nodejs-hello-world .
```

### Run Container

```bash
docker run -d -p 3000:3000 --name nodejs-hello-world nodejs-hello-world
```

### Verification

Open:

```
http://localhost:3000
```

### Result

Hello World from Node.js was displayed in the browser.

---

## 2. Python Application

### Folder

```text
docker/python-app/
```

### Files

- `app.py`
- `Dockerfile`

### Docker Image

```bash
docker build -t python-hello-world .
```

### Run Container

```bash
docker run -d -p 8000:8000 --name python-hello-world python-hello-world
```

### Verification

Open:

```
http://localhost:8000
```

### Result

Hello World from Python was displayed in the browser.

---

## 3. Java Application

### Folder

```text
docker/java-app/
```

### Files

- `HelloWorld.java`
- `Dockerfile`

### Docker Image

```bash
docker build -t java-hello-world .
```

### Run Container

```bash
docker run -d -p 8080:8080 --name java-hello-world java-hello-world
```

### Verification

Open:

```
http://localhost:8080
```

### Result

Hello World from Java was displayed in the browser.

---

## 4. Apache Application

### Folder

```text
docker/Apache-app/
```

### Files

- `index.html`
- `Dockerfile`

### Docker Image

```bash
docker build -t apache-hello-world .
```

### Run Container

```bash
docker run -d -p 8081:80 --name apache-hello-world apache-hello-world
```

### Verification

Open:

```
http://localhost:8081
```

### Result

Hello World from Apache was displayed in the browser.

---

## 5. React Application

### Folder

```text
docker/React-app/
```

### Files

- `package.json`
- `package-lock.json`
- `index.html`
- `src/App.jsx`
- `Dockerfile`

### Docker Image

```bash
docker build -t react-hello-world .
```

### Run Container

```bash
docker run -d -p 5173:5173 --name react-hello-world react-hello-world
```

### Verification

Open:

```
http://localhost:5173
```

### Result

Hello World from React was displayed in the browser.

---

## 6. Nginx Application

### Folder

```text
docker/nginx-app/
```

### Files

- `index.html`
- `Dockerfile`

### Docker Image

```bash
docker build -t nginx-hello-world .
```

### Run Container

```bash
docker run -d -p 8082:80 --name nginx-hello-world nginx-hello-world
```

### Verification

Open:

```
http://localhost:8082
```

### Result

Hello World from Nginx was displayed in the browser.

---

## Docker Containers

The applications were successfully run as Docker containers.

| Application | Container | Port | Status |
|---|---|---|---|
| Node.js | nodejs-hello-world | 3000 | Running |
| Python | python-hello-world | 8000 | Running |
| Java | java-hello-world | 8080 | Running |
| Apache | apache-hello-world | 8081 | Running |
| React | react-hello-world | 5173 | Running |
| Nginx | nginx-hello-world | 8082 | Running |

---

## Conclusion

All six Hello World web applications were successfully created, containerized using Docker, built into Docker images, and run as containers. Each application was verified by accessing its corresponding localhost URL in a web browser.
