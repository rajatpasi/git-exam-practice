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

