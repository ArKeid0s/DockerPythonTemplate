# DockerPythonTemplate
This is a template to run a Python app in a Docker container.

It will automatically install all the requirements in the container.

### Requirements
- Docker Desktop
- VSCode
- Remote Development (VSCode Extension)

### Instructions
Start the Docker Compose with the following command: `docker compose up --build -d`
- `--build` will make sure the requirements are installed correctly in case you added some
- `-d` will run the container in detached mode

After that, in the bottom-left corner of your VSCode, click the '><' button and select 'Attach to Running Container,' then select your container.

It will open a VSCode instance inside the container. You might need to click on 'Open Folder' and click on ../code and then open to open the project directory, you will also need to install the Python VSCode Extension.

Then you will be able to use the installed packages as if they were installed on your computer, but they are only in the container.

Once you are done, you can stop the container with the following command: `docker compose down`

### Debug inside container
The debug port is set at `5678` by default.

To debug I am using DebugPy. To use it you need to uncomment the commented lines in `main.py`.

After that you can start debugging and it will trigger the breakpoints.

### Example
The current example is using FastAPI, so at the start of the container, you can go to your web browser and visit http://localhost:80, you will see `{"Hello": "World"}`.
