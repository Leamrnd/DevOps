# TP DevOps Correction Docker

TP1


1-1	For which reason is it better to run the container with a flag -e to give the environment variables rather than put them directly in the Dockerfile?
To avoid storing sensitive information (like passwords) in plain text within the image.
1-2 Why do we need a volume to be attached to our postgres container?
A volume permits data persistence even if the container is deleted, it keeps the database intact.
1-3 Document your database container essentials: commands and Dockerfile

1-4 Why do we need a multistage build? And explain each step of this dockerfile
It separates the compilation phase (JDK + Maven) from the execution phase (JRE only), making the final image lighter and more secure.
1st step: Compile with Maven + JDK
2nd step: Run the app using a JRE
1-5 Why do we need a reverse proxy?
A reverse proxy centralizes access, secures traffic, redirects requests to the right service, and exposes a single URL.
1-6 Why is docker-compose so important?
It simplifies container management, like commands to build, start, stop or network in a unique file.

1-7 Document docker-compose most important commands.
docker-compose up -d        # Starts the containers  
docker-compose down         # Stops and removes the containers  
docker-compose build        # Rebuilds the images  
docker-compose logs         # Shows the logs  
docker-compose ps           # Lists running containers

1-8 Document your docker-compose file.
1-9 Document your publication commands and published images in dockerhub.
1-10 Why do we put our images into an online repo?
To easily share them between developers, deploy on other machines or servers, and version them properly.




TP2

Question 2-1: What are Testcontainers?
Testcontainers are Java libraries that let us run Docker containers during tests.
They automatically start a PostgreSQL container when integration tests run.

Question 2-2: Why use secrets?
For your Docker Hub credentials to stay private and secure, and are not visible in the code or logs.

Question 2-3: Why use needs: test-backend?
It means this job will only run if the tests pass.
Without it, Docker images could be built even if the code crashes

Question 2-4: Why do we push Docker images?
To save your app as an image on Docker Hub, so it can be reused and deployed anywhere.
