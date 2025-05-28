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

# Chapter2: Hello World App

 - In this chapter we’ll build a Django project that simply says “Hello, World” on the homepage.
   
 - This is the traditional way to start a new programming language or framework.

### Here step by step through **Chapter 2: Hello World App** for a Django project, covering:

1. Initial Setup
2. Create an App
3. URLs, Views, Models, Templates
4. Hello, World!
5. Git
6. Optional: GitHub and  SSH Key

I'll also give you a **structure** you can create manually, along with code and commands.

---

### Structure


![image](https://github.com/user-attachments/assets/4c1cac06-3d7c-4c4a-80d7-20126d2e5756)




###  1. Initial Setup

####  Install Django (if not already)

bash

```
pip install django
```

####  Start a Project

bash

```
django-admin startproject helloworld_project
cd helloworld_project
```

---

###  2. Create an App

bash

```
python manage.py startapp core
```

This creates a new Django app named `core`.

**Register the app in `settings.py`:**

python

```
# helloworld_project/settings.py
INSTALLED_APPS = [
    ...
    'core',
]
```

![image](https://github.com/user-attachments/assets/be2c7135-d223-4bd1-953d-fbdd322f6800)


---

### 3. URLs, Views, Models, Templates

#### Project-level URL setup:

python

```
# helloworld_project/urls.py
from django.contrib import admin
from django.urls import path path, include  #path:Lets you define URL patterns ,include: Lets you import URL patterns from another file

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('core.urls')),  # Link to app URLs
]
```

#### App-level URL setup:

Create `core/urls.py`:

python

```
# core/urls.py
from django.urls import path
from . import views

urlpatterns = [
    path('', views.hello_world, name='hello_world'),
]
```

#### Views:

python

```
# core/views.py
from django.http import HttpResponse

def hello_world(request):
    return HttpResponse("Hello, World!")
```

---

### 4. Hello, World!

Run the development server:

bash

```
python manage.py runserver
```

Visit [http://127.0.0.1:8000/](http://127.0.0.1:8000/) — you’ll see "Hello, World!"

---

![image](https://github.com/user-attachments/assets/840be6b1-d586-4c66-ad50-5f63461d2ec2)


### 5. Git

#### Initialize Git:

bash
```
git init
```

#### Create `.gitignore`:
- If you don't have a gitignore file ,then create it in your project root folder (e.g., HelloApp_Django), create a new file named: .gitignore

-  We can use this command in Powershell ,

```
  New-Item -Name ".gitignore" -ItemType "File"

```

![image](https://github.com/user-attachments/assets/6f782b43-93b4-47bf-aced-2fc365774ac9)



bash
```
__pycache__/
*.pyc
db.sqlite3
.env
```

![image](https://github.com/user-attachments/assets/18ba3044-ebb9-4304-8aa0-4a04a77d30ff)


#### Add and Commit:

bash

```
git add .
git commit -m "Initial Hello World Django app"
```

![image](https://github.com/user-attachments/assets/bd4678cb-065b-43c9-9758-c46df6bed150)



---

###  Optional: 6. GitHub

#### Create a repo on [GitHub](https://github.com/new)

#### Link it:

bash

```
git remote add origin git@github.com:yourusername/helloworld-django.git
git push -u origin main
```

---

### SSH Key

#### Generate an SSH Key:

bash

```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

* Press Enter 3 times to use defaults.
* Add key to GitHub: Copy the public key:


bash
```
cat ~/.ssh/id_ed25519.pub
```

Paste it into GitHub → Settings → SSH and GPG Keys → New SSH key.

---



# Chapter 3: Pages App

- In this chapter we will build, test, and deploy a Pages app with a homepage and about page.
  
-  We’ll learn about Django’s class-based views and templates which are the building blocks for the more complex web applications built later on in the book.


Here’s a GitHub-friendly, chapter-style breakdown and explanation for building a **Django Pages App** with homepage and about page using class-based views and templates:

---

 Here's a **concise algorithm-style breakdown** of the Django Pages App project setup using class-based views and templates:


### **Algorithm: Build a Django Pages App**

1. **Start Project Setup**

   * Install Django using `pip`.
   * Create a Django project: `django-admin startproject pages_project`.

2. **Create Pages App**

   * Inside the project directory, run: `python manage.py startapp pages`.
   * Add `'pages'` to `INSTALLED_APPS` in `settings.py`.

3. **Configure URLs**

   * Create `pages/urls.py` with paths for homepage and about page.
   * Include `pages.urls` in the project's main `urls.py`.

4. **Create Views**

   * Use `TemplateView` to define `HomePageView` and `AboutPageView` in `views.py`.

5. **Create Templates**

   * Inside `pages/templates/`, create `home.html` and `about.html` with simple HTML headings.

6. **Run the App**

   * Run `python manage.py runserver`.
   * Visit `http://127.0.0.1:8000/` for homepage and `/about/` for the about page.

7. **Initialize Git**

   * Run `git init`.
   * Create `.gitignore` to exclude files like `__pycache__/`, `*.pyc`, `db.sqlite3`, `.env`.
   * Commit initial setup with `git add .` and `git commit -m "Initial commit"`.

8. **(Optional)Push to GitHub**

   * Create a GitHub repository.
   * Add remote, rename default branch to `main`, and push code.

  **Set Up SSH**

   * Generate and add SSH key to GitHub for secure communication.

---

# Here is a step by step guide:

### 1. Initial Set Up

**Install Django**

bash

```
pip install django
```

### Check django version

bash

```
python -m django --version 

```

**Create a Django Project**

bash

```
django-admin startproject pages_project         #creates the project folder
cd pages_project                                 #directs to the folder
```

---

### 2. Create An App

**Create a new app called `pages`**

bash

```
python manage.py startapp pages                    #craetes an app inside project called page
```

**Add `'pages'` to `INSTALLED_APPS` in `pages_project/settings.py`**

python
```
INSTALLED_APPS = [
    ...
    'pages',                     #this important,if not give app will not be overlooked by compiler
]
```

![image](https://github.com/user-attachments/assets/7c1553df-2dd7-4be6-8fa4-11cc1b472501)


---

### 3. URLs, Views, Models, Templates

**Create URL configurations**

In `pages/urls.py` (create this file):

python

```
from django.urls import path
from .views import HomePageView, AboutPageView

urlpatterns = [
    path('', HomePageView.as_view(), name='home'),                                  #url for homepage
    path('about/', AboutPageView.as_view(), name='about'),                          #url for aboutpage
]
```

In `pages_project/urls.py`:

python

```
from django.contrib import admin
from django.urls import path, include                           #this is important or complier will not know about the include function

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('pages.urls')),                               #this will include the page url in pages_project's urls
]
```

---

### 4. Hello, World! (Class-based Views)

In `pages/views.py`:

python

```
from django.views.generic import TemplateView

# Renders the homepage template                    
class HomePageView(TemplateView):                     #function for homepage
    template_name = 'home.html'

# Renders the about page template
class AboutPageView(TemplateView):                    #function for aboutpage
    template_name = 'about.html'
```

---

### 5. Templates

Inside your app, create a folder: `pages/templates/`

Add `home.html`:

html

```
<h1>Welcome to the Homepage</h1>
```

Add `about.html`:

html

```
<h1>About This Project</h1>
```

---

### 6. Git

**Initialize a Git repository**

bash

```
git init
```

**Create a `.gitignore` file**

bash

```
echo "__pycache__/
*.pyc
db.sqlite3
.env
" > .gitignore
```

**Add and commit**

bash

```
git add .
git commit -m "Initial commit"
```

---

### 7. Optional: GitHub

**Create a new repo on GitHub**, then:

bash

```
git remote add origin https://github.com/your-username/django-pages-app.git
git branch -M main
git push -u origin main
```

---

#### SSH Key (Optional for GitHub Authentication)

**Generate SSH key (if not already set):**

bash

```

ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

**Add the key to ssh-agent:**


bash

```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

**Add your SSH public key to GitHub:**

bash

```
cat ~/.ssh/id_rsa.pub
```

Copy the output and paste it to GitHub → Settings → SSH and GPG Keys → New SSH key.



---


### Here is a structure of a the project ,



![image](https://github.com/user-attachments/assets/969ad90c-578d-430a-8e50-dc6dda8680ae)



Great! Here's your GitHub-friendly, chapter-style breakdown of the Django Message Board app, with step-by-step guidance and beginner-friendly comments in the code:

---

# Chapter 3: Message Board App with Django Admin

-  In this chapter wewill use a database for the first time to build a basic Message Board application where users can post and read short messages.
-  We’ll explore Django’s powerful built-in admin interface which provides a visual way to make changes to our data.
-  A beginner-friendly Django application where users can post and read short messages.
-   We'll explore Django’s ORM, model-view-template architecture, and its powerful built-in admin interface.


### Additional: 

- Thanks to the powerful Django ORM (Object-Relational Mapper), there is built-in support for multiple database backends: PostgreSQL, MySQL, MariaDB, Oracle, or SQLite.

- This means that we, as developers, can write the same Python code in a models.py file and it will automatically be translated into each database correctly.

-  The only configuration required is to update the DATABASES64 section of our config/settings.py file.
  
-   This is truly an impressive feature, For localdevelopment,Django defaults to using SQLite65 because it is file-based and therefore far simpler to use than the other database options, which require a dedicated server to be running separate from Django itself.

---

#  Algorithm

1. Set up a new Django project.
2. Create a new app called `board`.
3. Define a `Message` model with `name`, `content`, and `timestamp`.
4. Register the model in `admin.py`.
5. Configure URL routing.
6. Create views to list and post messages.
7. Add templates for displaying and adding messages.
8. Use Django Admin to manage messages visually.
9. Test and run the server.

---

# Step-by-Step Guide

### 1. Initial Setup

bash

```
django-admin startproject messageboard_project           #start project
cd messageboard_project                                  
python manage.py startapp board                           #create app
```

Add `board` to `INSTALLED_APPS` in `settings.py`.

python

```
# messageboard_project/settings.py
INSTALLED_APPS = [
    ...
    'board',                                #Register app
]
```

---

### 2. Create the Message Model

python

```
# board/models.py
from django.db import models

class Message(models.Model):                               # Here is where we declare name,content,time
    name = models.CharField(max_length=50)                              # Name of the user
    content = models.TextField()                                         # The actual message
    timestamp = models.DateTimeField(auto_now_add=True)                # Auto-added time

    def __str__(self):
        return f"{self.name}: {self.content[:20]}"                     # First 20 chars as preview

```

### Run migrations:

bash

```
python manage.py makemigrations
python manage.py migrate
```

---

### 3. Enable Django Admin

Create a superuser:

bash

```
python manage.py createsuperuser           

```

Register the model:

python

```
# board/admin.py
from django.contrib import admin
from .models import Message

admin.site.register(Message)             #register the message
```

---

### 4. Create Views

python 

```
# board/views.py
from django.shortcuts import render, redirect
from .models import Message
from django.utils import timezone

def home(request):
z    messages = Message.objects.order_by('-timestamp')                  # Show latest first
    return render(request, 'board/home.html', {'messages': messages})

def post_message(request):
    if request.method == 'POST':                            #gets values from user
        name = request.POST['name']                         #gets the name of user and assign them
        content = request.POST['content']                   #gets the content from user and assign them
        Message.objects.create(name=name, content=content, timestamp=timezone.now())   #auto assign time of user's post
        return redirect('home')                             #return user to home page
    return render(request, 'board/post_message.html')        #add the user post
```

---

### 5. URLs

Create a `urls.py` in `board` app:

python

```
# board/urls.py
from django.urls import path
from . import views

urlpatterns = [
    path('', views.home, name='home'),                             #url of home page in app
    path('post/', views.post_message, name='post_message'),        #url of post page in app         
]
```

Connect it to the project’s URL config:

python

```
# messageboard_project/urls.py
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('board.urls')),                      #url of app
]
```

---

### 6. Templates

Create a folder `templates/board/` and add:

**home.html**

html

```
<!-- board/templates/board/home.html -->
<h1>Message Board</h1>
<a href="{% url 'post_message' %}">Post a Message</a>
<ul>
  {% for msg in messages %}
    <li><strong>{{ msg.name }}</strong>: {{ msg.content }} <em>({{ msg.timestamp }})</em></li>
  {% empty %}
    <li>No messages yet.</li>
  {% endfor %}
</ul>
```

**post\_message.html**

html

```
<!-- board/templates/board/post_message.html -->
<h1>Post a Message</h1>
<form method="post">
  {% csrf_token %}
  <label>Name:</label><br>
  <input type="text" name="name" required><br>
  <label>Message:</label><br>
  <textarea name="content" required></textarea><br><br>
  <button type="submit">Post</button>
</form>
```

---

### 7. Run Server and Use Admin

bash

```
python manage.py runserver
```

* Visit `/` to see messages
* Visit `/post/` to add a message
* Visit `/admin/` to manage data with the superuser account

---

##  .gitignore

Create `.gitignore`:

gitignore

```
__pycache__/
*.pyc
db.sqlite3
.env
```


---

##  GitHub Steps

bash

```
git init
git add .
git commit -m "Initial commit for Message Board App"
gh repo create messageboard-app --public --source=. --remote=origin
git push -u origin main
```

---

# structure of code

![image](https://github.com/user-attachments/assets/2d052126-5118-4654-a317-c8db91ff083e)



---
