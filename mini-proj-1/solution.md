### **Working Solution:**

1. **Install Docker**:
   - Follow the installation instructions from the [Docker website](https://docs.docker.com/get-docker/).
   - Verify the installation by running:
     ```bash
     $ docker --version
     Docker version 24.0.7, build 24.0.7-0ubuntu2~22.04.1
     ```

2. **Create the Python Application**:
   - Create a new folder on your local machine for this project, e.g., `docker-hello-world`.
   - Inside this folder, create a file named [`app.py`](https://github.com/jkgaurav/docker-mini-projs/blob/main/mini-proj-1/docker-hello-world/app.py)

3. **Create a Dockerfile**:
   - A Dockerfile is a text file with instructions on how to build your Docker image. In the same folder as `app.py`, create a file named [`Dockerfile`](https://github.com/jkgaurav/docker-mini-projs/blob/main/mini-proj-1/docker-hello-world/Dockerfile) (no extension)

4. **Build the Docker Image**:
   - Open a terminal in the project folder and run the following command to build the Docker image:
     ```bash
     docker build -t hello-docker .
     ```
   - Explanation:
     - `docker build`: Command to build a Docker image.
     - `-t hello-docker`: Tags the image with the name `hello-docker`.
     - `.`: Tells Docker to look for the Dockerfile in the current directory.
    
5. **Run the Docker Container**:
   - After building the image, run the container with the following command:
     ```bash
     docker run hello-docker
     ```
  - **Expected Output**:
    ```bash
    Hello, Docker!
    ```
    
6. **Verify the Running Container**:
   - To see the list of running containers, you can use the command:
     ```bash
     $ docker ps -a
     CONTAINER ID   IMAGE          COMMAND           CREATED          STATUS                      PORTS     NAMES
     d64ab55148f7   hello-docker   "python app.py"   12 seconds ago   Exited (0) 11 seconds ago             boring_fermi
     ```
   - This will show all containers, including stopped ones.
---

### **Key Learning Points:**
- Understanding the basics of Docker images and containers.
- Building a Docker image using a Dockerfile.
- Running a container from a Docker image.
- How Dockerfile instructions work (FROM, WORKDIR, COPY, CMD).
- Checking running and stopped containers.

---

Let's move to the next [mini project]()!
