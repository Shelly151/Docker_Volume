# Docker Volume

Docker volumes are a popular and effective method for ensuring data persistence while working with containers. They provide a way to store and share data between containers and even persist data beyond the container lifecycle.

---

## **Installation**

To use Docker volumes, you must first install **Docker** and **Python**.

### **Step 1: Install Docker and Python**
Install both Docker and Python from their official sources:
- [Download Docker](https://docs.docker.com/get-docker/)
- [Download Python](https://www.python.org/downloads/)

### **Step 2: Verify Installations**
Once installed, verify their versions using the following commands:
```sh
# Check Docker version
docker --version

# Check Python version
python --version
```

---

## **Docker Volume Deployment**

### **Step 1: Start a New Container**
Run the following command to start an interactive terminal session in a new Node.js container using the latest image:
```sh
docker run -it node:latest
```

### **Step 2: List All Containers**
To view all Docker containers (both running and stopped), use:
```sh
docker container ls -a
```
#### Example Output:
```
CONTAINER ID   IMAGE          COMMAND                  CREATED              STATUS                      PORTS     NAMES
8363fec86c40   node:latest    "docker-entrypoint.s…"   About a minute ago   Exited (0) 24 seconds ago             inspiring_mccarthy
```

### **Step 3: Attach a Volume to a Container**
Mount a local directory as a volume inside a container:
```sh
docker run -it -v /Users/tanishqmacbook/Desktop/Docker_volume:/home/app node bash
```

### **Step 4: Create a Docker Volume**
Create a named volume for persistent storage:
```sh
docker volume create data
```

### **Step 5: Attach the Named Volume to a Container**
Mount the named volume **data** inside a container:
```sh
docker run -it -v data:/data node bash
```

### **Step 6: Use the Named Volume in Another Container**
To share the volume with another container, mount it in a new Ubuntu container:
```sh
docker run -it -v data:/myapp ubuntu
```

---

## **Conclusion**
Docker volumes provide an efficient way to persist and share data between containers. Using named volumes is the recommended approach for managing persistent data in containerized applications.

For more information, refer to the [Docker documentation](https://docs.docker.com/storage/volumes/).

