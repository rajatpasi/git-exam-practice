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

----------------------------------------------------------------------------------------------
# PRACTICAL 2: COMPREHENSIVE DEVOPS PIPELINE WITH JENKINS & BLUE OCEAN

## Aim

To install and configure Jenkins on a local Windows system and create an automated CI/CD pipeline integrated with Git and GitHub using Blue Ocean.

## Software Requirements

1. Windows 10/11
2. Java JDK (version supported by the installed Jenkins release)
3. Jenkins
4. Git and GitHub
5. Python
6. Blue Ocean plugin
7. Web browser

## Architecture

Developer → Git Repository → Jenkins → Build → Test → Deploy → Archive Artifacts

---

## Step 1: Install and verify Java

Jenkins requires Java to run.

Open PowerShell and execute:

```powershell
java -version
```

Expected: Java version details should appear.

If Java is not installed, install a JDK version supported by your Jenkins release and verify again.

## Step 2: Install Jenkins

1. Download the Jenkins Windows installer.
2. Run the installer.
3. Follow the installation wizard.
4. Keep the default port as 8080, unless it is already occupied.
5. Complete the installation.
6. Open your browser.

Enter:

```text
http://localhost:8080
```

The Jenkins Unlock screen should appear.

## Step 3: Unlock Jenkins

Jenkins asks for an initial administrator password.

Open PowerShell and execute:

```powershell
Get-Content "C:\ProgramData\Jenkins\.jenkins\secrets\initialAdminPassword"
```

If Jenkins uses its default data directory, the password will be displayed.

1. Copy the password.
2. Paste it into the Administrator password field.
3. Click Continue.

## Step 4: Create the first administrator user

On the Create First Admin User page, enter:

- Username: admin
- Password: Create your own password
- Confirm password: Enter the same password
- Full name: Your name
- Email address: Your email address

Click Save and Continue.

On the next screen, complete the Jenkins URL configuration and click Save and Finish.

Click Start using Jenkins.

Expected result: Jenkins dashboard should open successfully.

## Step 5: Install Blue Ocean plugin

1. Open Jenkins Dashboard.
2. Click Manage Jenkins.
3. Open Plugins.
4. Select Available plugins.
5. Search for Blue Ocean.
6. Select the Blue Ocean plugin and its required dependencies.
7. Click Install.
8. Wait until the installation completes.

If Blue Ocean is not available in your Jenkins installation, use the standard Pipeline interface as an alternative.

## Step 6: Create a project folder

Open Git Bash and execute:

```bash
cd ~/Desktop
mkdir DevOps-Project
cd DevOps-Project
```

Verify the current directory:

```bash
pwd
```

## Step 7: Create a Python application

Create the Python application:

```bash
notepad app.py
```

Paste the following code:

```python
print("Hello! Welcome to DevOps CI/CD Pipeline")
print("Application executed successfully")
```

Save the file and close Notepad.

Verify the file:

```bash
cat app.py
```

## Step 8: Initialize Git repository

Execute the following commands:

```bash
git init -b main
git add .
git status
git commit -m "Initial commit"
```

If Git asks for your identity, configure it:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

Repeat the commit if necessary.

## Step 9: Create a GitHub repository

1. Open https://github.com
2. Log in to your account.
3. Click the + icon.
4. Select New repository.
5. Enter repository name: DevOps-Project.
6. Select Public.
7. Click Create repository.

Copy the repository URL.

## Step 10: Connect the local repository to GitHub

Execute:

```bash
git remote add origin https://github.com/USERNAME/DevOps-Project.git
```

Replace USERNAME with your GitHub username.

Push the project:

```bash
git push -u origin main
```

Refresh GitHub and verify that app.py is visible.

## Step 11: Open Blue Ocean and create a pipeline

1. Open Jenkins Dashboard.
2. Click Open Blue Ocean.
3. Click Create a new Pipeline.
4. Select where your source code is stored.
5. Select GitHub if using your GitHub repository.
6. Authorize Jenkins to access GitHub if requested.
7. Select the DevOps-Project repository.
8. Select the main branch.

Blue Ocean will check the repository for an existing Jenkinsfile.

If it does not find one, select Create Pipeline.

## Step 12: Create the Build stage

The pipeline editor will open.

1. Select the Build stage.
2. Click Add step.
3. Select Windows Batch Script.
4. Enter the following script:

```bat
echo "Compiling application"
python --version
python app.py
```

5. Save the stage.
6. Enter description: Build Step Created.
7. Select the main branch.
8. Click Save & Run.

The Build stage will be created.

## Step 13: Create the Test stage

1. Open the pipeline editor.
2. Click Add stage after Build.
3. Name the stage Test.
4. Click Add step.
5. Select Windows Batch Script.
6. Enter:

```bat
echo "Running Tests"
python -c "assert 2 + 3 == 5"
```

7. Save the stage.
8. Enter description: Test Step Created.
9. Select main.
10. Click Save & Run.

Expected result: Test stage should execute successfully.

## Step 14: Create the Deploy stage

1. Click Add stage after Test.
2. Enter stage name: Deploy.
3. Click Add step.
4. Select Windows Batch Script.
5. Enter:

```bat
echo "Deploying application"
echo "Deployment completed successfully"
```

6. Save the stage.
7. Enter description: Deploy Step Created.
8. Select main.
9. Click Save & Run.

Expected result: Deploy stage should execute successfully.

## Step 15: Create Build Artifact

Add an artifact creation step to the Build stage.

Select Windows Batch Script and enter:

```bat
echo Build Version 1.0 > build-info.txt
```

This creates a file named build-info.txt.

Add an Archive the artifacts step to the pipeline and configure:

```text
Artifacts: build-info.txt
```

Enable fingerprinting if the option is available.

Save and run the pipeline.

Expected result: The build artifact should be archived successfully.

## Step 16: Verify the complete pipeline

Open Blue Ocean and observe the pipeline.

The stages should appear in the following order:

1. Start
2. Build
3. Test
4. Deploy
5. End

Successful stages should show green status indicators.

Open the latest pipeline execution and check the logs of each stage.

## Step 17: Perform error testing

To understand pipeline failure handling, modify the Python application.

Open Git Bash:

```bash
notepad app.py
```

Replace the application code with:

```python
print("This is a buggy version of the app");
```

For a deliberate test failure, change the Test stage script to:

```bat
echo "Running automated tests"
python -c "assert 2 + 3 == 6"
```

Save the changes and execute the pipeline again.

Expected result:

- Build stage may execute successfully.
- Test stage will fail.
- The pipeline will show a failed status.
- Deploy stage will not execute if it depends on the failed Test stage.

This demonstrates how Jenkins identifies errors during pipeline execution.

## Step 18: Fix the error

Open the Blue Ocean pipeline editor.

Replace the Test stage script with:

```bat
echo "Running automated tests"
python -c "assert 2 + 3 == 5"
```

Ensure the application code is also correct:

```python
print("Hello! Welcome to DevOps CI/CD Pipeline")
print("Application executed successfully")
```

Save and run the pipeline again.

Expected result: All pipeline stages should execute successfully.

## Step 19: Final verification

Verify the following:

- Jenkins dashboard is accessible.
- Blue Ocean plugin is installed.
- GitHub repository is connected.
- Build stage is successful.
- Test stage is successful.
- Deploy stage is successful.
- Build artifact is archived.
- Final pipeline status is successful.

## Result

Successfully installed and configured Jenkins, integrated GitHub with Jenkins using Blue Ocean, created Build, Test and Deploy stages, archived build artifacts, and tested both successful and failed pipeline executions.

## Conclusion

This practical demonstrated the implementation of a CI/CD pipeline using Jenkins and Blue Ocean. The integration of GitHub with Jenkins enabled source code management and automated pipeline execution. Different stages such as Build, Test, Deploy and Artifact Archiving were configured and executed successfully. Error testing was also performed to understand pipeline failure handling and troubleshooting.

-------------------------------------------------------------------------------------------
PRACTICAL
3: DOCKER BASICS
============================================================ AIM: To
install Docker Desktop, verify it, run a container, create a Dockerfile
and build/run a custom image.

REQUIREMENTS: Windows, WSL 2, Docker Desktop, Command Prompt or
PowerShell.

1.  Check WSL: wsl –version If not installed, open Administrator
    PowerShell and run: wsl –install Restart if requested.

2.  Install Docker Desktop: Download from
    https://www.docker.com/products/docker-desktop/ Install with WSL 2
    backend where available, restart if requested, open Docker Desktop
    and wait for Docker Engine to run.

3.  Verify: docker –version docker info

4.  Run the test container: docker run hello-world Expected: Docker
    displays a message confirming that the installation works.

5.  Create a folder: mkdir docker-test cd docker-test

6.  Create Dockerfile: notepad Dockerfile Enter: FROM ubuntu CMD
    [“echo”, “Hello BCA Students”] Save. The filename must be exactly
    Dockerfile, not Dockerfile.txt. If saved incorrectly: ren
    Dockerfile.txt Dockerfile

7.  Build image: docker build -t bca-image .

8.  Run image: docker run bca-image Expected: Hello BCA Students

9.  Verify: docker images docker ps docker ps -a

RESULT: Docker was verified; hello-world ran; a Dockerfile was created
and a custom image was built and executed.

CONCLUSION: Docker images package applications and dependencies;
containers run those images in isolated environments.

SCREENSHOTS: WSL version; Docker Desktop; docker version; hello-world;
Dockerfile; build output; run output; Docker Desktop container list.

============================================================ PRACTICAL
4: DOCKER IMAGE FROM REMOTE REPOSITORY (DOCKER COMPOSE)
============================================================ AIM: The
journal describes Docker Compose for multi-container applications. The
visible screenshots specifically show a Node.js frontend Dockerfile
cloning a remote GitHub repository, installing dependencies, exposing
port 3000 and starting the application. A complete Compose YAML or
complete multi-service configuration is not visible in the source
screenshots.

1.  Create folder in Command Prompt: mkdir new-docker cd new-docker

2.  Create Dockerfile: notepad Dockerfile

Enter the following, replacing the URL with the actual frontend
repository you are authorized to use:

Use Node.js image

FROM node:18 # Set working directory WORKDIR /app # Install Git RUN
apt-get update && apt-get install -y git # Clone frontend project RUN
git clone https://github.com/USERNAME/REPOSITORY.git . # Install
dependencies RUN npm install # Expose React default port EXPOSE 3000 #
Start React application CMD [“npm”, “start”]

Save. Ensure the filename is Dockerfile, not Dockerfile.txt. If needed:
ren Dockerfile.txt Dockerfile

3.  Verify: dir

4.  Build: docker build -t react-frontend .

5.  Run: docker run -p 3000:3000 react-frontend

6.  Open browser: http://localhost:3000 The app should load if its
    package configuration starts the app on port 3000.

7.  Verify container in another terminal: docker ps Stop with Ctrl+C in
    the running terminal, or use docker stop CONTAINER_ID.

NOTE: Docker Compose uses a compose.yaml or docker-compose.yml file to
define related services. The provided screenshots do not show enough
detail to reproduce a particular frontend/backend/database Compose file.
Do not invent service names, ports, passwords or database settings.

RESULT: A frontend project was cloned from a remote Git repository,
packaged into a Docker image and run through port 3000.

CONCLUSION: Docker images make applications portable. Docker Compose can
manage multiple related containers when a valid service configuration is
supplied.

SCREENSHOTS: folder; Dockerfile; filename; build output; container run;
browser at localhost:3000; docker ps.

============================================================ PRACTICAL
5: INTRODUCTION TO ANSIBLE
============================================================ AIM: To
install Ansible on Windows using WSL and create playbooks to automate
basic tasks.

REQUIREMENTS: Windows, WSL, Ubuntu, Ansible.

1.  Install WSL from Administrator PowerShell: wsl –install Restart if
    requested.

2.  Launch Ubuntu. Create your own Linux username and password. Do not
    use credentials from another student’s journal.

3.  Update Ubuntu: sudo apt update

4.  Install Ansible: sudo apt install ansible -y

5.  Verify: ansible –version

6.  Create folder: mkdir ~/ansible_lab cd ~/ansible_lab

7.  Create playbook: nano basic_playbook.yml

Enter this YAML, replacing YOUR_LINUX_USERNAME with your actual Ubuntu
username. Keep the indentation:

------------------------------------------------------------------------

-   name: Basic Ansible Automation hosts: localhost connection: local
    tasks:
    -   name: Create a text file file: path:
        /home/YOUR_LINUX_USERNAME/ansible_file.txt state: touch

    -   name: Write content to a file copy: content: “This file is
        created using Ansible automation” dest:
        /home/YOUR_LINUX_USERNAME/ansible_message.txt

Save nano: Ctrl+O, Enter, Ctrl+X.

8.  Run playbook: ansible-playbook basic_playbook.yml

9.  Verify files: ls /home/YOUR_LINUX_USERNAME/ cat
    /home/YOUR_LINUX_USERNAME/ansible_message.txt

Expected content: This file is created using Ansible automation

RESULT: WSL and Ansible were installed; a YAML playbook created files
and wrote content automatically.

CONCLUSION: Ansible uses YAML playbooks for configuration management and
repetitive task automation.

SCREENSHOTS: WSL; Ubuntu; apt update; Ansible installation; ansible
version; playbook code; playbook run; created files and cat output.

============================================================ PRACTICAL
6: KUBERNETES BASICS
============================================================ AIM: To set
up a local Kubernetes cluster using Minikube, deploy a containerized
application using kubectl, expose it as a service and access it through
a browser.

REQUIREMENTS: Windows, WSL, Docker Desktop, kubectl, Minikube, browser.

1.  Verify WSL: wsl –version If needed, install from Administrator
    PowerShell: wsl –install

2.  Install and start Docker Desktop. Ensure Docker Engine is running.
    Verify: docker –version

3.  Install kubectl using:
    https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/
    Verify: kubectl version –client

4.  Install Minikube: https://minikube.sigs.k8s.io/docs/start/ Verify:
    minikube version

5.  Start cluster using Docker driver: minikube start –driver=docker

6.  Verify cluster: kubectl cluster-info kubectl get nodes Expected:
    Minikube node should show Ready.

7.  Create NGINX deployment: kubectl create deployment nginx
    –image=nginx Expected: deployment.apps/nginx created

8.  Check pods: kubectl get pods Wait until the NGINX pod shows Running
    and READY 1/1.

9.  Expose deployment: kubectl expose deployment nginx –type=NodePort
    –port=80 Expected: service/nginx exposed

10. Check service: kubectl get services

11. Open application: minikube service nginx Open the URL displayed by
    Minikube in a browser. Expected page: Welcome to nginx!

12. Verify all resources: kubectl get all

RESULT: A Minikube cluster was started; an NGINX deployment and pod were
created; the deployment was exposed as a service and accessed in a
browser.

CONCLUSION: Kubernetes manages containerized workloads using
deployments, pods and services. Minikube provides a local Kubernetes
learning environment.

SCREENSHOTS: WSL; Docker Desktop; kubectl version; Minikube version;
cluster start; cluster-info; nodes; deployment; pods; service; NGINX
browser page; kubectl get all.

============================================================ GENERAL
TROUBLESHOOTING
============================================================

GIT: origin already exists git remote -v git remote set-url origin
https://github.com/USERNAME/REPOSITORY.git

GIT: push rejected because remote contains changes Inspect the remote
first. If local and remote histories are unrelated: git pull origin main
–allow-unrelated-histories –no-rebase Resolve conflicts, commit the
merge, then: git push -u origin main Do not force push as a first
solution.

GIT BASH: nano command not found Use: notepad filename Do not use nano
unless it is installed.

JENKINS: Python not recognized Check in PowerShell: python –version
Jenkins runs as a Windows service and may not use the same PATH as your
logged-in user. Ensure Python is available to the Jenkins service.

JENKINS: Jenkinsfile not found Check that it is named exactly
Jenkinsfile, not Jenkinsfile.txt, and is committed to the selected
branch.

DOCKER: daemon not running Open Docker Desktop and wait for Docker
Engine to start.

DOCKER: Dockerfile not found Run dir and verify the exact filename
Dockerfile.

ANSIBLE: YAML error Use spaces, not tabs. Check indentation, filename
and Linux file paths.

KUBERNETES: Minikube cannot start Ensure Docker Desktop is running:
minikube status minikube start –driver=docker

KUBERNETES: pod not running kubectl get pods kubectl describe pod
POD_NAME Replace POD_NAME with the actual pod name.

============================================================ END OF
DEVOPS LAB PRACTICALS

-----------------------------------------------------------------------------------------

final - 3 

Step 1 – Install WSL through CMD
WSL (Windows Subsystem for Linux) allows Linux environments to run on Windows. Docker Desktop uses WSL 2 for its Linux containers.
1. Click the Windows Start button.
2. Search for CMD.
3. Right-click Command Prompt.
4. Select Run as administrator.
Enter:
wsl --install


Wait for installation to complete.

If Windows asks you to restart, restart your computer.








kapilarya.com


Screenshot 1: Capture the CMD window showing the WSL installation.
Step 2 – Download and install Docker Desktop
1. Open the official Docker website.
2. Download Docker Desktop for Windows.
3. Run the installer.
4. Select the WSL 2 backend option if prompted.
5. Complete installation.
6. Restart your computer if required.
7. Open Docker Desktop and wait until it shows that Docker is running.

Download Docker Desktop








community.element14.com


Screenshot 2: Capture Docker Desktop running successfully.
Step 3 – Verify Docker installation
Open Git Bash or CMD and execute:
docker --version


Then:
docker info


Expected: Docker version information and server details should appear. If docker info shows a server connection error, Docker Desktop may not be running yet.

Screenshot 3: Capture the Docker version and successful server information.
Step 4 – Run your first Docker container
Execute:
docker run hello-world


Expected output includes:
Hello from Docker!
This message shows that your installation appears to be working correctly.


This confirms Docker can download and run a container.

Screenshot 4: Capture the Hello from Docker output.
Step 5 – Clone a GitHub repository
Open Git Bash.

Navigate to Downloads:
cd ~/Downloads


Clone the repository:
git clone YOUR_GITHUB_REPOSITORY_URL


Replace the URL with the GitHub repository URL you are supposed to use.

For example:
git clone https://github.com/USERNAME/portfolio.git


Enter the downloaded folder:
cd portfolio


Check the files:
ls


Screenshot 5: Capture the successful Git clone and the list of repository files.
Step 6 – Create a Dockerfile
Inside the cloned project folder, execute:
notepad Dockerfile


If Notepad asks whether to create a new file, click Yes.

Paste this code:
FROM nginx:alpine

COPY . /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]


Save the file as Dockerfile (without .txt) and close Notepad.

This Dockerfile:
- FROM: Uses the Nginx web server image.
- COPY: Copies your website files into the container.
- EXPOSE: Specifies port 80.
- CMD: Starts the Nginx server.
Screenshot 6: Capture the Dockerfile code in Notepad.
Step 7 – Build the Docker image
In Git Bash, make sure you are inside the project folder.

Execute:
docker build -t portfolio .


Explanation:
- docker build: Builds an image.
- -t portfolio: Gives the image the name portfolio.
- .: Uses the current folder as the build context.
Wait until the build completes successfully.

Screenshot 7: Capture the successful Docker image build.
Step 8 – Verify the Docker image
Execute:
docker images


Expected: You should see an image named portfolio.

Example:
REPOSITORY	TAG
portfolio	latest
nginx	alpine

Screenshot 8: Capture the Docker images list.
Step 9 – Run the Docker container
Execute:
docker run -d -p 8081:80 --name portfolio-container portfolio


Explanation:
- -d: Runs in the background.
- -p 8081:80: Maps Windows port 8081 to container port 80.
- --name: Assigns a name to the container.
- portfolio: Uses the image we built.
Verify:
docker ps


Expected: The portfolio-container should appear with status Up.

Screenshot 9: Capture the running container.
Step 10 – Open the Dockerized website
Open Google Chrome.

Enter:

-----------------------------------------------------------------------------------------------

final 4 
Lab 4: Continuous Integration and Deployment using Git, Jenkins and Docker

Aim: To create a CI/CD pipeline using Git, Jenkins and Docker to build and deploy a website automatically.

Tools required: Git Bash, GitHub, Jenkins, Docker Desktop and Google Chrome.

This practical is different from Practical 3. Here, Jenkins will automatically build the Docker image, run the container and verify it.
Step 1 – Clone the GitHub repository
Open Git Bash.

Go to Downloads:
cd ~/Downloads


Clone the repository used in your friend's journal:
git clone https://github.com/jasleenkaur/Portfolio-MScDevops.git


Enter the project folder:
cd Portfolio-MScDevops


Check the files:
ls


You should see the project files, such as README.md, index.html, script.js and style.css if those files are present in the repository.

If the repository URL is unavailable or returns an error, send me a screenshot rather than using a different repository.

Screenshot 1: Capture the successful Git clone and project files.
Step 2 – Create a Dockerfile
In Git Bash, while inside Portfolio-MScDevops, execute:
touch Dockerfile


Open it:
notepad Dockerfile


Paste the following code:
FROM nginx:alpine

COPY . /usr/share/nginx/html

EXPOSE 80


Save the file and close Notepad.

Verify:
cat Dockerfile


Explanation:
- FROM nginx:alpine – Uses the Nginx web server.
- COPY . /usr/share/nginx/html – Copies website files into the container.
- EXPOSE 80 – Specifies the web server port.
Screenshot 2: Capture the Dockerfile code.
Step 3 – Add Docker to Windows PATH and restart Jenkins
This is important because Jenkins must be able to recognize Docker commands.

A. Add Docker to PATH
1. Press Win + R.
2. Type:
sysdm.cpl


3. Click Advanced.
4. Click Environment Variables.
5. Under System variables, select Path.
6. Click Edit → New.
Add the Docker executable folder.

Your friend's PDF shows:
C:\Users\Admin\AppData\Local\Programs\DockerDesktop\resources\bin


Replace Admin with your Windows username if Docker is installed in that location. Check the actual location first; don't add a path that doesn't exist.

7. Click OK on all windows.

B. Restart Jenkins
1. Press Win + R.
2. Type:
services.msc


3. Find Jenkins.
4. Right-click Jenkins.
5. Click Restart.
Screenshot 3: Capture Docker PATH configuration and Jenkins service restarted.
Step 4 – Create a new Jenkins Pipeline
1. Open Chrome.
2. Open Jenkins:
http://localhost:8080


3. Log in to Jenkins.
4. Open Blue Ocean (if installed).
5. Select Create a new Pipeline.
6. Select GitHub.
7. Connect your GitHub account if prompted.
8. Select the Portfolio-MScDevops repository.
9. Create the pipeline.
If Blue Ocean is not installed, tell me before proceeding; we can check your Jenkins setup.

Screenshot 4: Capture the Jenkins pipeline configuration and connected GitHub repository.
Step 5 – Add Build stage
In the Jenkins Pipeline editor:
1. Add a stage named Build.
2. Select Windows Batch Script.
3. Enter these commands:
where docker
docker --version
docker build -t portfolio .


The commands:
- where docker checks the Docker executable location.
- docker --version verifies Docker.
- docker build -t portfolio . builds the Docker image.
Screenshot 5: Capture the Build stage and commands.
Step 6 – Add Run Docker Container stage
1. Click the + after the Build stage.
2. Select Windows Batch Script.
3. Name the stage:
Run Docker Container


4. Enter the command from your PDF:
docker rm -f portfolio-container >nul 2>&1 & docker run -d -p 8081:80 --name portfolio-container portfolio


This removes an existing container with the same name (if present) and starts a new one.

Screenshot 6: Capture the Run Docker Container stage.
Step 7 – Add Verify Docker Container stage
1. Click the + after the Run Docker Container stage.
2. Select Windows Batch Script.
3. Name the stage:
Verify Docker Container


4. Enter:
docker ps


This verifies whether the Docker container is running.

Screenshot 7: Capture the Verify Docker Container stage.
Step 8 – Run the Jenkins Pipeline
1. Save the pipeline.
2. Click Run.
3. Wait for all stages to complete.
4. Check that Build, Run Docker Container and Verify Docker Container are successful.








ratheeshcloud.com


Screenshot 8: Capture the successful Jenkins pipeline execution.
Step 9 – Verify in terminal and open the website
Open Git Bash or CMD and execute:
docker ps


Check that portfolio-container is running.

Now open Chrome:
Website URL
http://localhost:8081/
