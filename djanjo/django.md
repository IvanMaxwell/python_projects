# Chapter 1: Initial Set Up of Django      // Under-development
 
 - This chapter covers how to properly configure your computer to work on Django projects.
 
 - We start with an overview of the command line and how to install the latest version of Django and Python.
 
 - Then we discuss virtual environments, git, and working with a text editor.
 
 - By the end of this chapter you’ll be ready to create and modify new Django projects in just a few keystrokes.

 - Before we explore about Django we need to know about some general inforamation,

---

# What is Django?

- Django is a high-level Python web framework that enables rapid development of secure and maintainable websites.

 - It encourages clean, pragmatic design and follows the "Don't Repeat Yourself" (DRY) principle.

 - 2003: Created by developers at the Lawrence Journal-World newspaper to manage news content.
  
 - 2005: Open-sourced and named after jazz guitarist Django Reinhardt.
  
 - Now maintained by the Django Software Foundation, it is one of the most popular web frameworks for Python.

---
 # Command line in django

**Using the Command Line:**

- The command line is essential for Django development, used for setting up and managing projects.

**To Open the Command Line follow these steps,**
 
 
Mac: Open Terminal from

Applications > Utilities > Terminal


Windows: Open Terminal using

Use PowerShell (recommended over Command Prompt) or use git bash 

**Note: vs code has default terminal build-in connected with powershell**

![image](https://github.com/user-attachments/assets/8d72b467-d777-49ba-b07e-00f2e064bde1)

---

| Command      | Description                 |
| ------------ | --------------------------- |
| `cd`         | Navigate into a directory   |
| `cd ..`      | Move up one directory       |
| `ls` / `dir` | List files (Mac / Windows)  |
| `pwd`        | Show current directory path |
| `mkdir`      | Create a new directory      |
| `touch`      | Create a new file on mac      |


---

# How to install django:

**Installing Python**

Python is required for Django development.

Follow the steps below to install it on your system.

---

**For macOS**
Check if Python is installed:

terminal
```
python3 --version
```

If not installed, use Homebrew:

terminal
```
brew install python
```
---
**For Windows,**

Download Python from the official site:

https://www.python.org/downloads/windows/

Run the installer:

Make sure to check the box that says "Add Python to PATH"

Note:If the python isn't working check out this website for guide,https://realpython.com/installing-python/

---

**For Linux**

Use your package manager. Example for Debian/Ubuntu:

terminal
```
sudo apt update  
sudo apt install python3 python3-pip
```

Verify Installation
Run the following in your terminal or PowerShell:

terminal
```
python3 --version
pip3 --version
```
If you see version numbers, Python and pip are successfully installed.

---


# installation of django

 
**1. Make sure Python is already installed in our system for django**
 terminal
```
python --version 
 ```
---
**3. Install django by using pip**

**Command:**
terminal
``` 
pip install django 
```

The temrinal will show you the following in proccces of insatllation,

![image](https://github.com/user-attachments/assets/3edeb66f-d541-4cf8-b973-2646262fd218)

---

**3. To check django version:** 
 terminal
 ```
py -m django --version
```

---

# Virutual environment

**Using Virtual Environments**

Virtual environments are isolated containers that hold the dependencies for a specific Python project.

This prevents conflicts between projects using different package versions 

---

**Why Use Virtual Environments?**

- Keeps project dependencies separate

- Avoids version conflicts

- Ensures consistent environments across systems

- Standard practice in Python development

---

**Note:**

- In python we have a  built-in Python module used to create isolated virtual environments

- we also have a  third-party tool called pipenv that combines virtual environment management and package management into a single workflow.


---

**Example Workflows**

| Platform    | Create Environment      | Activate Environment        |
| ----------- | ----------------------- | --------------------------- |
| Windows     | `python -m venv .venv`  | `.venv\Scripts\activate`    |
| macOS/Linux | `python3 -m venv .venv` | `source .venv/bin/activate` |

---

**basic of venv:**

terminal

- python -m venv .venv            # Create environment
- .venv\Scripts\activate          # Activate on Windows
- source .venv/bin/activate       # Activate on macOS/Linux
- pip install django              # Manually install packages
- pip freeze > requirements.txt   # Save dependencies



---


# Installation of GIT


### What is Git?

**Git** is a **version control system** used to track changes in code, collaborate with other developers, and revert to earlier versions of a project when needed.

It works similarly to “track changes” in Microsoft Word or Google Docs, but is built specifically for software development.

* [Official Git Website](https://git-scm.com/)
* [What is Version Control? (Wikipedia)](https://en.wikipedia.org/wiki/Version_control)

---

### Install Git

#### On macOS

**Terminal:**

```terminal
brew install git
```

**Why:**
This command uses **Homebrew**, a macOS package manager, to download and install Git. It’s the recommended way for Mac users.

---

#### On Windows

1. Visit [Git for Windows](https://gitforwindows.org/)
2. Click the **Download** button
3. Follow the installation prompts

**Why:**
This provides Git along with Git Bash (a command-line tool), which allows you to use Git commands on Windows easily.

---

### Configure Git (One-Time Setup)

After installation, you need to tell Git your name and email address. This information will be attached to your commits.

**Terminal:**

```terminal
git config --global user.name "Your Name"
git config --global user.email "yourname@email.com"
```

**Why:**
Git uses this information to record who made each change. You can update it anytime using the same commands.

---

### Verify the Installation

**Terminal:**

```terminal
git --version
```

**Why:**
This checks if Git is correctly installed and displays the version number.

---

### Common Use Cases for Git

* Initialize and manage local repositories
* Commit and track file changes
* Collaborate via GitHub, GitLab, etc.
* Safely branch and merge features or fixes

---

### Text Editors
 
The final step is our text editor. While the command line is where we execute commands for our programs, a text editor is where the actual code is written. 
 
The computer doesn’t care what text editor you use–the end result is just code–but a good text editor can provide helpful hints and catch typos for you.
 
 Experienced developers often prefer using either Vim27 or Emacs28, both decades-old, text-only
 editors with loyal followings.
 
 However each has a steep learning curve and requires memorizing many different keystroke combinations. I don’t recommend them for newcomers 

 
 Modern text editors combine the same powerful features with an appealing visual interface.
 
 My current favorite is Visual Studio Code29 which is free, easy to install, and enjoys widespread
 popularity.
 
 If you’re not already using a text editor, download and install Visual Studio Code30
 now.
 
---

# Create a Hello World App



```

# Create project directory
cd ~/Desktop
mkdir helloworld && cd helloworld

# Initialize pipenv environment and install Django
pipenv install django~=3.1.0
pipenv shell

# Start Django project
django-admin startproject config .

# Create the 'pages' app
python manage.py startapp pages

# Register the 'pages' app in config/settings.py
# Add 'pages' to INSTALLED_APPS

# Create views in pages/views.py
cat << EOF > pages/views.py
from django.http import HttpResponse

def homePageView(request):
    return HttpResponse('Hello, World!')
EOF

# Create urls.py in pages and configure route
cat << EOF > pages/urls.py
from django.urls import path
from .views import homePageView

urlpatterns = [
    path('', homePageView, name='home'),
]
EOF

# Update config/urls.py to include pages app
# Add: path('', include('pages.urls'))

# Apply migrations
python manage.py migrate

# Start development server
echo "Visit http://127.0.0.1:8000/ to see 'Hello, World!'"
python manage.py runserver

# Initialize Git and commit project
git init
git add -A
git commit -m "Initial commit: Hello World Django app"

# GitHub setup instructions
# Visit https://github.com/new and create a new private repo 'hello-world'
# Then run the following (replace with your repo URL):
# git remote add origin git@github.com:yourusername/hello-world.git
# git push -u origin master

# If you encounter SSH issues:
# 1. Generate an SSH key: ssh-keygen -t ed25519 -C "your_email@example.com"
# 2. Start ssh-agent and add your key: eval "$(ssh-agent -s)" && ssh-add ~/.ssh/id_ed25519
# 3. Add your public key to GitHub: https://github.com/settings/ssh/new

```


Great! Let's go step by step through **Chapter 2: Hello World App** for a Django project, covering:

1. Initial Setup
2. Create an App
3. URLs, Views, Models, Templates
4. Hello, World!
5. Git
6. GitHub
7. SSH Key

I'll also give you a **GitHub repository structure** you can create manually, along with code and commands.

---

### 🧱 1. Initial Setup

#### ✅ Install Django (if not already)

```bash
pip install django
```

#### ✅ Start a Project

```bash
django-admin startproject helloworld_project
cd helloworld_project
```

---

### 🏗️ 2. Create an App

```bash
python manage.py startapp core
```

This creates a new Django app named `core`.

**Register the app in `settings.py`:**

```python
# helloworld_project/settings.py
INSTALLED_APPS = [
    ...
    'core',
]
```

---

### 🌐 3. URLs, Views, Models, Templates

#### Project-level URL setup:

```python
# helloworld_project/urls.py
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('core.urls')),  # Link to app URLs
]
```

#### App-level URL setup:

Create `core/urls.py`:

```python
# core/urls.py
from django.urls import path
from . import views

urlpatterns = [
    path('', views.hello_world, name='hello_world'),
]
```

#### Views:

```python
# core/views.py
from django.http import HttpResponse

def hello_world(request):
    return HttpResponse("Hello, World!")
```

---

### 👋 4. Hello, World!

Run the development server:

```bash
python manage.py runserver
```

Visit [http://127.0.0.1:8000/](http://127.0.0.1:8000/) — you’ll see "Hello, World!"

---

### 🔧 5. Git

#### Initialize Git:

```bash
git init
```

#### Create `.gitignore`:

```bash
__pycache__/
*.pyc
db.sqlite3
.env
```

#### Add and Commit:

```bash
git add .
git commit -m "Initial Hello World Django app"
```

---

### ☁️ 6. GitHub

#### Create a repo on [GitHub](https://github.com/new)

#### Link it:

```bash
git remote add origin git@github.com:yourusername/helloworld-django.git
git push -u origin main
```

---

### 🔐 7. SSH Key

#### Generate an SSH Key:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

* Press Enter 3 times to use defaults.
* Add key to GitHub: Copy the public key:

```bash
cat ~/.ssh/id_ed25519.pub
```

Paste it into GitHub → Settings → SSH and GPG Keys → New SSH key.

---

### 🗂️ Suggested Repo Structure

```
helloworld-django/
├── core/
│   ├── __init__.py
│   ├── views.py
│   ├── urls.py
│   └── ...
├── helloworld_project/
│   ├── settings.py
│   ├── urls.py
│   └── ...
├── db.sqlite3
├── manage.py
└── .gitignore
```

---

### ✅ Want me to generate a GitHub-ready zip for this project or use your GitHub username to create a repo?

Let me know and I’ll help further!

