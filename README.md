# Flask Python Rest API Template

### This project repo serves as a quickstart template for getting a lightweight flask api up and running.

## Get Started - Installing Dependencies

##### 1. You will need Python runtime version 3 or above installed on your laptop first. 

##### 2. In bash terminal enter the commands to create a virtual environment and activate it.

#### python3.10 -m venv .venv
#### source .venv/bin/activate

##### 3. Open the command palette in VSCODE. Select the .venv as your python interpretor. 
#### FilePath: command palette > Python: Select Interpretor > .venv

##### 4. Open a new bash in the terminal and run the following command to install all dependecies and libraries. Make sure you are in the .venv bash or this will not work. 
#### pip install -r requirements.txt

##### 5. After verifying that everything has installed correctly run the following command in bash terminal to launch the local enviornment. You should see a Warning message that this is a development server, do not use it in production. This is because you need dockerized container images to run the app and serve on all devices. See section after this for more detials. The local enviornment should now be running on localhost http://127.0.0.1:5000

#### flask run

##### 6. After you verify this is working we can end the local enviornment anytime by pressing keys "control^ + c" 

## How to build dockerized container images

##### 1. Docker Desktop is an application to help you manage your images and containers. Download it and install it here if you have not already: https://www.docker.com/products/docker-desktop/.

##### 2. Notice how we have a file called "Dockerfile". Inside you will find docker dependencies to virtualize the app so that the image inside the container has every dependency from requirements.txt. 

##### 3. Run the following command in .venv bash terminal to build your docker image. Note: Inside the brackets [-t rest-apis-flask-python] name is optional, but tags the image, giving it a name. It can be handy for later! The final . at the end of the command is not a mistake; it tells the command what to build. The . means "the current directory".

#### docker build [-t rest-apis-flask-python] . 

##### In order to run your docker image enter the following command in your .venv bash terminal. Notice how you can specify the port range

#### docker run -d -p 5000:5000 rest-apis-flask-python
