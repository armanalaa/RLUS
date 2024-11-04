**Docker Instructions**

Follow these steps to set up, build, and run the Docker container for this project. The containerized environment ensures that all dependencies are managed within Docker, providing a consistent and isolated setup.

**1. Set Up Your Project Directory**
Before building the Docker container, ensure you have the absolute path to your project directory, which we'll refer to as <absolute_path_to_project>. Replace this placeholder with the actual path in the commands below.

**2. Building the Docker Image**
Navigate to your project directory:


cd <absolute_path_to_project>

Then, build the Docker image with the following command:


docker build -t <project_name> .

-t <project_name>: Tags the image with a name (<project_name>). 

Replace <project_name> with a meaningful name for this project.

.: Specifies the current directory as the build context.

This command will create a Docker image with all the necessary dependencies and configurations defined in the Dockerfile.

**3. Running the Docker Container**
   
Run the Docker container using the command below:

docker run -v <absolute_path_to_project>:/app <project_name>

-v <absolute_path_to_project>:/app: Mounts the project directory on your host machine (<absolute_path_to_project>) to the /app directory within the Docker container. This allows you to access files within the container and save outputs back to your local system.

<project_name>: The name of the Docker image created in the build step.

**4. Viewing Real-Time Logs**

You can monitor the container's output in real-time by using the following command:

docker logs -f <project_name>

-f: Follows the log output, displaying updates in real-time.
<project_name>: Replace with the name of your Docker container.

**5. Copying Results and Logs to Host System: After the container has completed its execution, you may need to retrieve the results and logs stored within the container. Use the following commands to copy these files to the host system:**

[sudo] docker cp <project_name>:/app/results ./results
[sudo] docker cp <project_name>:/app/logs ./logs
docker cp <project_name>:/app/results ./results: Copies the results directory from the container to a local ./results folder.
docker cp <project_name>:/app/logs ./logs: Copies the logs directory from the container to a local ./logs folder.

[sudo]: Some systems may require sudo to access Docker commands, particularly on Linux. Remove [sudo] if not necessary on your system.

**Additional Information**

**Sample Size (rho values):** Stored in the ./results folder on the host system after copying.
**Execution Times: ** Logged and stored in the ./logs folder on the host system after copying.

By following these steps, you can efficiently manage and monitor the containerized execution of this project, ensuring that results and logs are readily accessible on your host system.
