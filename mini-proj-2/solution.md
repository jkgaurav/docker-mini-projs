### **Working Solution:**

1. **Create the Flask Web Application**:
   - First, create a new project folder called `docker-flask-app`.
   - Inside this folder, create a file named [`app.py`](https://github.com/jkgaurav/docker-mini-projs/blob/main/mini-proj-2/docker-flask-app/app.py)

   - The important part here is that the Flask app is set to run on `host='0.0.0.0'`. This tells Flask to make the app accessible to any IP address, not just `localhost`.

2. **Create a Requirements File**:
   - Create a [`requirements.txt`](https://github.com/jkgaurav/docker-mini-projs/blob/main/mini-proj-2/docker-flask-app/requirements.txt) file in the same folder
   - This file will list the Python dependencies needed by your app, which Docker will install later.

3. **Create the Dockerfile**:
   - In the same folder as `app.py`, create a file named [`Dockerfile`](https://github.com/jkgaurav/docker-mini-projs/blob/main/mini-proj-2/docker-flask-app/Dockerfile)

4. **Build the Docker Image**:
   - Open a terminal in the `docker-flask-app` folder and run the following command to build the Docker image:
     ```bash
     docker build -t flask-app .
     ```
   - Explanation:
     - `docker build`: Builds the Docker image.
     - `-t flask-app`: Tags the image as `flask-app`.
     - `.`: Tells Docker to look for the Dockerfile in the current directory.

5. **Run the Docker Container with Port Binding**:
   - Now, run the container and map port 5000 inside the container to port 5000 on your host machine:
     ```bash
     docker run -p 5000:5000 flask-app
     ```
   - Explanation:
     - `-p 5000:5000`: Maps port 5000 on your host to port 5000 inside the container, allowing external access to the app.
    
6. **Test the Application**:
   - Open a browser and or curl `http://localhost:5000`. You should see:
     ```
     $ curl http://localhost:5000
      Hello, Dockerized Flask!
     ```
     
7. **Check Running Containers**:
   - To see the running container, use:
     ```bash
     $ docker ps
     CONTAINER ID   IMAGE       COMMAND                  CREATED          STATUS          PORTS                                       NAMES
     c7bd8b80e88b   flask-app   "flask run --host=0.…"   18 minutes ago   Up 18 minutes   0.0.0.0:5000->5000/tcp, :::5000->5000/tcp   youthful_pascal
     ```
---

### **Key Learning Points:**
- Introduction to port binding with Docker (`-p` flag).
- Understanding how Docker networking works, allowing external access to services running inside containers.
- How to work with environment variables and exposed ports in Docker.
- Hands-on experience with a simple web server running inside a container.

---

Let's move to the next [mini project]()
