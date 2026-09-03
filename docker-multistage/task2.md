# Docker Multi-Stage Build Homework

## Student Information

**Name:** Amishi Patidar
**Enrollment Number:** YOUR_ENROLLMENT_NUMBER

---

## Task 1: Multi-Stage Docker Application

### Docker Image Build

Command used:

```bash
docker build -t multi-stage-hello-world .
```

### Run Container

Command used:

```bash
docker run -d -p 8080:3000 --name multi-stage-hello-world multi-stage-hello-world
```

### Application Verification

Application URL:

```
http://localhost:8080
```

Application output:

```
Hello World from Docker Multi-Stage Build!
```

### Docker PS Verification

Command:

```bash
docker ps
```

Output:

```
multi-stage-hello-world   0.0.0.0:8080->3000/tcp
```

This confirms that the multi-stage Docker application is running and accessible through port 8080.

### Screenshots

**Application Running**

Add the screenshot showing:

```
Hello World from Docker Multi-Stage Build!
```

**Docker PS**

Add the screenshot showing:

```
multi-stage-hello-world — 0.0.0.0:8080->3000/tcp
```

---

## Task 3: Docker Application Deployment

Three different types of applications were deployed using Docker:

| Application | Docker Image | Host Port |
|---|---|---:|
| Node.js | `nodejs-hello-world` | 3000 |
| Python | `python-hello-world` | 8000 |
| Java | `java-hello-world` | 8083 |

All three applications were successfully deployed and accessed through Docker containers.

### Java Application Verification

Application URL:

```text
http://localhost:8083
```

Application output:

```
Hello from Java
```

**Important:** Use `8083` for Java here, not `8080`, because `8080` is being used by your multi-stage application.

---

## Conclusion

The multi-stage Docker application was successfully built and deployed. The application was verified through the browser on port 8080, and the running container was verified using `docker ps`. Three different application types — Node.js, Python, and Java — were also deployed using Docker.
