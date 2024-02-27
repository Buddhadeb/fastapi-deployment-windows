# FastAPI Deployment as windows service

Today i am writing this documentation for me and those who are looking for batter solution for deploy fastapi application on windows server as windows services.this will help you easy to make production ready application with scalable solution.

Below is our requirments:

- [Python](https://www.python.org/)
- [Non-Sucking Service Manager(NSSM)](https://nssm.cc/)
- [HTTP and reverse proxy server(NGINX)](https://nginx.org/en/)
- Windows system

## Python

Let's harness the power of Python with the lightning-fast FastAPI framework to build a robust REST API. With Python's versatility and FastAPI's efficiency, we're poised to create a cutting-edge web service that will elevate your application to new heights.

## Non-Sucking Service Manager (NSSM)

NSSM is a tool that allows us to easily create and manage Windows services. We'll use NSSM to run our FastAPI application as a service.

## HTTP and Reverse Proxy Server (NGINX)

NGINX will serve as our HTTP server and reverse proxy. It will forward requests from clients to our FastAPI service, providing an additional layer of security and scalability.

## Windows System

Of course, we'll need a Windows system to deploy our FastAPI application as a service. This could be a local development machine or a production server.

## Setting Up FastAPI

First, let's set up our FastAPI application. We'll create a basic example to demonstrate the deployment process.

## 1.Setting Up the Environment

Open a command prompt:

```bash
# Open Command Prompt on Windows and navigate to one of your drives. For example, let's choose the G drive.
mkdir fastapi-demo  # Create a folder named fastapi-demo
cd fastapi-demo  # Change the current directory to fastapi-demo
virtualenv env  # Create a virtual environment directory to manage Python dependencies
env\Scripts\activate  # Activate the virtual environment
pip install fastapi uvicorn  # Install FastAPI(framework) and Uvicorn(ASGI web server) using pip

```

## 2. Creating the FastAPI Application

Open a code editor and create a file named **main.py:**

```py
from fastapi import FastAPI
import uvicorn

app = FastAPI()


@app.get("/")
def index():
    return "API is running"


if __name__ == "__main__":
    uvicorn.run("main:app", port=8020)

```

## 3.Running the FastAPI Application

In the command prompt, run the following command to start the FastAPI application:

```bash
python main.py
```

## 4.Checking the Application

Open a web browser and go to [http://127.0.0.1:8020/](http://127.0.0.1:8020/) to verify that the FastAPI application is running.

Next, we'll proceed to deploy our FastAPI application as a Windows service using NSSM.
[Read Deployment](deployment.md)
