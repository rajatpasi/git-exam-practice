# git-exam-practice



\# Git and GitHub Lab 1



\## Exercise 1: Create a Git Repository and Push to GitHub



\### Step 1: Create project folder

```bash

mkdir git-exam-practice

cd git-exam-practice

```



\### Step 2: Create Python file

```python

print("Welcome to Git and GitHub Lab 1")

```



\### Step 3: Initialize Git

```bash

git init -b main

```



\### Step 4: Add and commit files

```bash

git add .

git commit -m "new file created"

```



\### Step 5: Connect GitHub repository

```bash

git remote add origin https://github.com/rajatpasi/git-exam-practice.git

```



\### Step 6: Push to GitHub

```bash

git push -u origin main

```



\## Exercise 2: Branching and Merging



\### Step 1: Create login branch

```bash

git checkout -b login

```



\### Step 2: Create login.py

```python

print("Login page created successfully")

```



\### Step 3: Add and commit

```bash

git add .

git commit -m "login file added"

```



\### Step 4: Push login branch

```bash

git push -u origin login

```



\### Step 5: Switch to main branch

```bash

git checkout main

```



\### Step 6: Merge login branch

```bash

git merge login

```



\### Step 7: Push main branch

```bash

git push origin main

```



\## Exercise 3: Create and Resolve Merge Conflict



\### Step 1: Switch to login branch

```bash

git checkout login

```



\### Step 2: Modify app.py

```python

print("This is a file on which I am creating a merge conflict")

```



\### Step 3: Commit changes

```bash

git add .

git commit -m "creating merge conflict"

```



\### Step 4: Switch to main

```bash

git checkout main

```



\### Step 5: Modify app.py again

```python

print("I changed the content")

```



\### Step 6: Commit changes

```bash

git add .

git commit -m "changed the content"

```



\### Step 7: Merge login branch

```bash

git merge login

```



\### Step 8: Resolve merge conflict



Open app.py and remove all conflict markers. Keep:



```python

print("Git merge conflict resolved successfully")

```



\### Step 9: Commit resolved file

```bash

git add .

git commit -m "merge conflict solved"

```



\### Step 10: Push changes

```bash

git push origin main

```



\## Final Verification



```bash

git branch

git status

git log --oneline --graph --all

git remote -v

```



\*\*Result:\*\* Successfully created a Git repository, uploaded files to GitHub, created and merged branches, and resolved a merge conflict.  

# PRACTICAL 2: JENKINS CI PIPELINE USING PYTHON

## Objective
To create a Jenkins Continuous Integration (CI) pipeline using Python, Pytest, GitHub and Jenkins.

## Step 1: Check installations

Open PowerShell:

```powershell
git --version
python --version
```

Open Jenkins in browser:

`http://localhost:8080`

Log in to Jenkins dashboard.

## Step 2: Create project folder

```powershell
cd $HOME\Documents
mkdir DevOps-Exam
cd DevOps-Exam
```

## Step 3: Create Python application

```powershell
Set-Content app.py 'print("Hello from Jenkins CI Pipeline")'
```

## Step 4: Create Python test file

```powershell
Set-Content test_app.py 'def test_addition():'
Add-Content test_app.py '    assert 2 + 3 == 5'
```

## Step 5: Install Pytest and execute test

```powershell
python -m pip install pytest
python -m pytest -v
```

Expected output:

```text
test_app.py::test_addition PASSED
1 passed
```

## Step 6: Create README file

```powershell
Set-Content README.md "# Jenkins CI Pipeline Practical"
```

## Step 7: Initialize Git

```powershell
git init -b main
git add .
git commit -m "Initial commit"
```

If Git asks for identity:

```powershell
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Repeat the commit if required.

## Step 8: Create GitHub repository

1. Open GitHub.
2. Click New Repository.
3. Repository name: DevOps-Exam.
4. Select Public.
5. Click Create Repository.
6. Copy the repository URL.

## Step 9: Connect local project to GitHub

Replace the URL with your repository URL.

```powershell
git remote add origin https://github.com/USERNAME/DevOps-Exam.git
git push -u origin main
```

## Step 10: Create Jenkinsfile

```powershell
notepad Jenkinsfile
```

Paste the following pipeline code:

```groovy
pipeline {
    agent any

    stages {
        stage('Initialize') {
            steps {
                echo 'Starting Jenkins CI Pipeline'
                bat 'python --version'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'python -m pip install pytest'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'python -m pytest -v'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Python application'
                bat 'python app.py'
            }
        }
    }

    post {
        success {
            echo 'CI Pipeline completed successfully!'
        }
        failure {
            echo 'CI Pipeline failed. Check console output.'
        }
    }
}
```

Save the file as Jenkinsfile without a `.txt` extension.

Push Jenkinsfile to GitHub:

```powershell
git add .
git commit -m "Add Jenkins pipeline"
git push origin main
```

## Step 11: Create Jenkins Pipeline Job

1. Open Jenkins dashboard.
2. Click New Item.
3. Enter project name: DevOps-Exam.
4. Select Pipeline.
5. Click OK.

## Step 12: Configure GitHub in Jenkins

Under the Pipeline section, configure:

| Field | Value |
|---|---|
| Definition | Pipeline script from SCM |
| SCM | Git |
| Repository URL | Your GitHub URL |
| Credentials | None (public repository) |
| Branch | */main |
| Script Path | Jenkinsfile |

Click Save.

## Step 13: Execute Jenkins Pipeline

1. Open your Jenkins job.
2. Click Build Now.
3. Open the latest build number.
4. Click Console Output.

## Step 14: Verify final output

Expected output:

```text
Starting Jenkins CI Pipeline

Python version displayed

Successfully installed pytest

test_app.py::test_addition PASSED

Hello from Jenkins CI Pipeline

CI Pipeline completed successfully!

Finished: SUCCESS
```

## Result

Successfully created and executed a Jenkins CI pipeline using Python, Pytest, GitHub and Jenkins.

Practical 3 – Dockerize a GitHub Repository
Aim: To set up Docker, clone a GitHub repository, create a Dockerfile, build a Docker image and run the application inside a Docker container.
Step 1: Install WSL
Open Command Prompt as Administrator:
wsl --install


Restart your computer if prompted.

Check WSL:
wsl --version


Step 2: Download and install Docker Desktop








it-connect.fr


1. Open the official Docker Desktop download page.
2. Download Docker Desktop for Windows.
3. Run the installer.
4. Select the WSL 2 backend if prompted.
5. Finish installation and open Docker Desktop.
6. Wait until Docker Desktop shows that it is running.
Step 3: Verify Docker installation
Open Command Prompt or Git Bash:
docker --version


Expected output:
Docker version 29.x.x


Your version may be different.
Step 4: Run your first Docker container
docker run hello-world


Expected output:
Hello from Docker!
This message shows that your installation appears to be working correctly.


This confirms Docker is installed and working.
Step 5: Clone the GitHub repository
Open Git Bash.

Navigate to Downloads:
cd /c/Users/Admin/Downloads


Clone the repository from your practical manual:
git clone https://github.com/jasjeenkaur/Portfolio-MScDevops.git


Navigate inside the project:
cd Portfolio-MScDevops


Check the files:
ls


The manual shows files such as:
README.md
index.html
script.js
styles.css


Step 6: Create a Dockerfile
In Git Bash:
touch Dockerfile


Open the file:
notepad Dockerfile


Paste this complete code:
FROM nginx:alpine

COPY . /usr/share/nginx/html

EXPOSE 80


Save the file as Dockerfile (without .txt).

Explanation:
- FROM nginx:alpine – Uses the lightweight Nginx web server image.
- COPY . /usr/share/nginx/html – Copies website files into the Nginx web directory.
- EXPOSE 80 – Documents the port used by the web server.
Step 7: Build the Docker image
Run this command inside the project folder:
docker build -t portfolio .


Explanation:
- docker build – Builds a Docker image.
- -t portfolio – Gives the image the name portfolio.
- . – Uses the current directory as the build context.
Wait until the build completes successfully.
Step 8: Verify the Docker image
docker images


Expected output includes:
REPOSITORY    TAG       IMAGE ID
portfolio     latest    xxxxx


Step 9: Run the Docker container
docker run -d -p 8081:80 --name portfolio-container portfolio


Explanation:
- -d – Runs the container in the background.
- -p 8081:80 – Maps host port 8081 to container port 80.
- --name – Assigns the container name.
- portfolio – Uses the Docker image.
If a container with this name already exists, remove it first:
docker rm -f portfolio-container


Then run the docker run command again.
Step 10: Verify the container and open the website
Check running containers:
docker ps


Expected output should show:
CONTAINER ID   IMAGE       STATUS
xxxxxx         portfolio   Up


Open your browser:
Open Dockerized Portfolio Website







dev.to


Practical 3 completed

All commands – Quick revision for exam
Use this as your last-minute command sheet.

# 1. Install WSL (run in CMD as Administrator)
wsl --install

# 2. Verify Docker
docker --version

# 3. Run first container
docker run hello-world

# 4. Navigate to Downloads
cd /c/Users/Admin/Downloads

# 5. Clone repository
git clone https://github.com/jasjeenkaur/Portfolio-MScDevops.git

# 6. Enter project folder
cd Portfolio-MScDevops

# 7. Create Dockerfile
touch Dockerfile

# 8. Build Docker image
docker build -t portfolio .

# 9. Verify image
docker images

# 10. Run Docker container
docker run -d -p 8081:80 --name portfolio-container portfolio

# 11. Verify container
docker ps

Lab 3 – Setting Up Docker, Clone and Dockerize a GitHub Repository
Below is the complete practical from beginning to end, prepared for your own computer using your own GitHub repository and newly created website files.

We will follow the same main workflow as your friend's college PDF, but create your own project instead of using your friend's repository.

Aim: To install Docker, clone a GitHub repository, create a Dockerfile, build a Docker image and run a website inside a Docker container.
1. Software requirements
- Windows 10/11
- WSL 2
- Docker Desktop
- Git
- GitHub account
- Command Prompt
- Web browser
2. Install WSL
Open Command Prompt as Administrator.

Execute:
wsl --install


Restart your computer if prompted.

Verify installation:
wsl --version


3. Install Docker Desktop








manula.com


1. Visit Docker Desktop.
2. Download Docker Desktop for Windows.
3. Run the installer.
4. Select the WSL 2 backend if prompted.
5. Complete installation.
6. Open Docker Desktop.
7. Wait until Docker Engine is running.
4. Verify Docker installation
Open CMD:
docker --version


Expected: Docker version information.
5. Run your first container
docker run hello-world


Expected output:
Hello from Docker!
This message shows that your installation appears to be working correctly.


6. Create a new GitHub repository
1. Open GitHub.
2. Sign in.
3. Click the + icon and select New repository.
4. Repository name: My-Docker-Portfolio.
5. Select Public.
6. Leave README, .gitignore and License unchecked.
7. Click Create repository.








karttur.github.io


Copy your repository URL. It should look like:
https://github.com/YOUR_USERNAME/My-Docker-Portfolio.git


7. Clone your repository
Open CMD and execute:
cd %USERPROFILE%\Downloads


Clone your repository. Replace YOUR_USERNAME with your GitHub username:
git clone https://github.com/YOUR_USERNAME/My-Docker-Portfolio.git


Enter the folder:
cd My-Docker-Portfolio


Check your location:
cd


8. Create the website files
We will create two files.

File 1 – index.html
notepad index.html


Paste:
<!DOCTYPE html>
<html>
<head>
    <title>My Docker Portfolio</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Welcome to My Portfolio</h1>
    <h2>Docker Practical - Lab 3</h2>
    <p>This website is running inside a Docker container.</p>
</body>
</html>


Save and close Notepad.

File 2 – style.css
notepad style.css


Paste:
body {
    font-family: Arial;
    text-align: center;
    background-color: lightblue;
    padding: 100px;
}

h1 {
    color: darkblue;
}


Save and close Notepad.

Check the files:
dir


You should see index.html and style.css.
9. Upload files to GitHub
Execute these commands:
git add .


git commit -m "Add portfolio website"


git push


Your website source code is now uploaded to GitHub.
10. Create Dockerfile
Execute:
notepad Dockerfile


Paste the following code:
FROM nginx:alpine

COPY . /usr/share/nginx/html

EXPOSE 80


Save the file with the exact name Dockerfile, without .txt.

Explanation:
Command	Purpose
FROM nginx:alpine	Uses Nginx as the base image
COPY . /usr/share/nginx/html	Copies website files into the Nginx directory
EXPOSE 80	Documents the web server port

11. Build Docker image
Execute:
docker build -t portfolio .


Wait until the image is built successfully.
12. Verify Docker image
docker images


Expected: An image named portfolio should appear.
13. Run Docker container
Execute:
docker run -d -p 8081:80 --name portfolio-container portfolio


Explanation:
- -d – Runs container in the background.
- -p 8081:80 – Maps host port 8081 to container port 80.
- --name – Assigns a container name.
- portfolio – Specifies the image.
14. Verify running container
Execute:
docker ps


Your portfolio-container should show status Up.
15. Open Dockerized website
Open Chrome and enter:
Open My Docker Portfolio







learn.ibots-bonn.de


16. Result
Successfully installed and configured Docker, created a new GitHub repository, cloned the repository, created website files and a Dockerfile, built a Docker image, and deployed the portfolio website inside a Docker container.
17. Conclusion
Docker was used to containerize a portfolio website using the Nginx web server. The website was successfully accessed through the browser using port mapping.

Screenshots to attach to your practical file
Take your own screenshots while performing the practical.
1. WSL installation and verification.
2. Docker Desktop running.
3. Docker version verification.
4. Successful hello-world execution.
5. Creation of GitHub repository.
6. Cloning GitHub repository.
7. index.html and style.css code.
8. Dockerfile code.
9. Docker image build output.
10. Docker images command output.
11. Docker container running using docker ps.
12. Portfolio website opened at localhost:8081.
Quick revision – All important commands
Keep this command sheet for your exam:
:: Install WSL
wsl --install

:: Verify WSL
wsl --version

:: Check Docker
docker --version

:: Run first container
docker run hello-world

:: Navigate to Downloads
cd %USERPROFILE%\Downloads

:: Clone GitHub repository
git clone https://github.com/YOUR_USERNAME/My-Docker-Portfolio.git

:: Enter project folder
cd My-Docker-Portfolio

:: Check files
dir

:: Upload files to GitHub
git add .
git commit -m "Add portfolio website"
git push

:: Build Docker image
docker build -t portfolio .

:: Verify image
docker images

:: Run Docker container
docker run -d -p 8081:80 --name portfolio-container portfolio

:: Verify container
docker ps


Important viva questions
Question	Answer
1. What is Docker?	A platform for building and running applications in containers.
2. What is a Docker image?	A template used to create containers.
3. What is a Docker container?	An isolated environment where an application runs.
4. What is a Dockerfile?	A file containing instructions to build a Docker image.
5. What is Docker Hub?	A platform to store and share Docker images.
6. What is Nginx?	A web server used to serve web applications.
7. What is WSL?	Windows Subsystem for Linux.
8. What does docker build do?	Builds a Docker image.
9. What does docker run do?	Creates and starts a container.
10. What does -p 8081:80 mean?	Maps host port 8081 to container port 80.
11. What does -d mean?	Runs a container in the background.
12. What does docker ps do?	Displays running containers.

Important practical note: If docker run says the container name is already in use, execute:
docker rm -f portfolio-container

