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

# Chapter 4: Blog App

---

##  Project Setup


### 1. Create and Activate Virtual Environment


bash

```
mkdir django-blog
cd django-blog
````

### 2. Install Django:

bash

```

pip install django
```

### 3. Start Django Project:

bash

```
django-admin startproject myblog .
```

### 4. Run Server to Test Setup:

bash

```
python manage.py runserver
```

Go to: [http://127.0.0.1:8000/](http://127.0.0.1:8000/)

---

##  Create the Blog App:

bash
```
python manage.py startapp blog
```

Add `'blog'` to `INSTALLED_APPS` in `myblog/settings.py`.

python

```
# myblog/settings.py

INSTALLED_APPS = [
    ...
    'blog',                                #Register app
]
```


---

##  Create Post Model:

In `blog/models.py`:

python
```
from django.db import models
from django.utils import timezone

class Post(models.Model):
    title = models.CharField(max_length=200)
    content = models.TextField()
    date_posted = models.DateTimeField(default=timezone.now)
    author = models.CharField(max_length=100)

    def __str__(self):
        return self.title
```

---

##  Migrate Database

bash

```
python manage.py makemigrations
python manage.py migrate
```

---

##  Register Model in Admin

In `blog/admin.py

python

```
from django.contrib import admin
from .models import Post

admin.site.register(Post)
```

Create superuser:

bash

```
python manage.py createsuperuser
```

Login at: [http://127.0.0.1:8000/admin/](http://127.0.0.1:8000/admin/)

---

##  Create Blog View

In `blog/views.py`:

python
```
from django.shortcuts import render
from .models import Post

def home(request):
    posts = Post.objects.all()
    return render(request, 'blog/home.html', {'posts': posts})
```

---

## Configure URLs

### In `blog/urls.py`:

python
```
from django.urls import path
from . import views

urlpatterns = [
    path('', views.home, name='blog-home'),
]
```

### In `myblog/urls.py`:

python
```
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('blog.urls')),
]
```

---

##  Add Templates

### Note :This has style tag included  

Create `blog/templates/blog/home.html`:
html
```
<html>
 <head>
 <title>Django blog</title>

 <style>

    
    h1{
        font-size: 3rem;
        display: flex;
        justify-content: center;
        align-items: baseline;
        font-display: block;
        font-family: 'Times New Roman', Times, serif;
        text-transform: uppercase;
        background-color: rgb(98, 69, 128);

    }

     a{
        color:rgb(218, 181, 218);
        background-color: rgb(98, 69, 128);
        display: flex;
        justify-content: center;
    }

    .a1{
        font-family: 'Times New Roman', Times, serif;
        font-size: 1.7em;
        text-transform: capitalize;
        display: grid;
        align-items: center;
        justify-content: center;
        
    }


 </style>

</head>
 <body>
 <header>
 <h1><a href="{% url 'home' %}">Django blog</a></h1>
 </header>
 <div class="a1">
 {% block content %}
 {% endblock content %}
 </div>
 </body>
 </html>    
```

---

##  Run the Server
bash
```
python manage.py runserver
```

Visit: [http://127.0.0.1:8000/](http://127.0.0.1:8000/)

---

##  Features

* Display blog posts on homepage
* Admin panel to manage posts
* Simple model and view setup

---

##  Next Steps (Optional)

* Add a `Post Detail` page
* Link posts to Django `User` model
* Use Bootstrap for styling
* Add forms for creating/editing posts

---



# Chapter 5: Forms in django

## Adding customize add page in blog app for users


---

#  Add "Create Post" Functionality

We'll walk through the steps to let users add posts via a web form.

---

## 1.  Create the Post Form

Create a new file: `blog/forms.py`

```python
from django import forms
from .models import Post

class PostForm(forms.ModelForm):
    class Meta:
        model = Post
        fields = ['title', 'content', 'author']
```

---

## 2.  Create the View to Handle the Form

Update `blog/views.py`:

python

```
from django.shortcuts import render, redirect
from .models import Post
from .forms import PostForm

def home(request):
    posts = Post.objects.all()
    return render(request, 'blog/home.html', {'posts': posts})

def create_post(request):
    if request.method == 'POST':
        form = PostForm(request.POST)
        if form.is_valid():
            form.save()
            return redirect('blog-home')
    else:
        form = PostForm()
    return render(request, 'blog/create_post.html', {'form': form})
```

---

## 3.  Add URL for "Add Post" Page

In `blog/urls.py`:

python

```
from django.urls import path
from . import views

urlpatterns = [
    path('', views.home, name='blog-home'),
    path('add/', views.create_post, name='create-post'),
]
```

---

## 4.  Create the HTML and CSS Template for the Form

Create file: `blog/templates/blog/create_post.html`

html

```
<!DOCTYPE html>
<html>
<head>
    <title>Add New Post</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 40px;
            background-color: #f4f4f4;
        }

        h1 {
            color: #333;
            margin-bottom: 20px;
        }

        form {
            background: #fff;
            padding: 25px;
            border: 1px solid #140b0b;
            border-radius: 8px;
            max-width: 500px;
        }

        form p {
            margin-bottom: 15px;
        }

        button {
            padding: 10px 15px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 4px;
        }

        button:hover {
            background-color: #218838;
        }

        a.back {
            display: inline-block;
            margin-top: 20px;
            text-decoration: none;
            color: #007bff;
        }

        a.back:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <h1>Add New Post</h1>
    <form method="post">
        {% csrf_token %}
        {{ form.as_p }}
        <button type="submit">Post</button>
    </form>
    <a href="{% url 'blog-home' %}">Back to Home</a>
</body>
</html>

```

---

## 5.  Add Link to "Add Post" on the Homepage and also edit css

Update `blog/templates/blog/home.html`:

html

```
<!DOCTYPE html>
<html>
<head>
    <title>Blog Home</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 40px;
            background-color: #f9f9f9;
        }

        h1 {
            color: #333;
            margin-bottom: 20px;
        }

        .post {
            background: #fff;
            border: 1px solid #ddd;
            padding: 20px;
            margin-bottom: 20px;
            border-radius: 8px;
        }

        .post h2 {
            margin: 0;
            color: #2c3e50;
        }

        .post small {
            color: #888;
        }

        a.button {
            display: inline-block;
            padding: 10px 15px;
            background-color: #007bff;
            color: white;
            text-decoration: none;
            border-radius: 4px;
            margin-bottom: 20px;
        }

        a.button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>
    <h1>Blog Posts</h1>

    <a href="{% url 'create-post' %}" class="button">+ Add New Post</a>

    {% for post in posts %}
        <div class="post">
            <h2>{{ post.title }}</h2>
            <p>{{ post.content }}</p>
            <small>By {{ post.author }} on {{ post.date_posted }}</small>
        </div>
    {% empty %}
        <p>No posts yet.</p>
    {% endfor %}
</body>
</html>

```

---

##  Final Step: Test It!

Run the server:

bash

```
python manage.py runserver
```

Then go to:

* Home: [http://127.0.0.1:8000/](http://127.0.0.1:8000/)
* Add Post: [http://127.0.0.1:8000/add/](http://127.0.0.1:8000/add/)

---

# Chapter 6: Newspaper App


Great! You're now looking to build a **basic content management system (CMS)-style Newsreader app** in Django, where:

* Journalists can create, edit, and delete articles.
* Only the **author** of an article can edit or delete it (permission logic).
* Any authenticated user can **comment** on an article (introducing **foreign keys**).
* We'll also include authentication with Django's built-in user model.

---


## ✅ 1. Project Setup

### Terminal Commands

```bash
# Create project and app
django-admin startproject newsreader .
python manage.py startapp news
```

### Install dependencies

```bash
pip install django
pip freeze > requirements.txt
```

---

## ✅ 2. Configure the Project

### In `newsreader/settings.py`

* Add `'news'` to `INSTALLED_APPS`.

```python
INSTALLED_APPS = [
    ...,
    'news',
]
```

* Add templates directory (optional):

```python
import os
TEMPLATES[0]['DIRS'] = [os.path.join(BASE_DIR, 'templates')]
```

---

## ✅ 3. Create Models (Articles & Comments)

### `news/models.py`

```python
from django.db import models
from django.contrib.auth.models import User
from django.urls import reverse

class Article(models.Model):
    title = models.CharField(max_length=200)
    body = models.TextField()
    author = models.ForeignKey(User, on_delete=models.CASCADE, related_name='articles')
    created_at = models.DateTimeField(auto_now_add=True)

    def __str__(self):
        return self.title

    def get_absolute_url(self):
        return reverse('article_detail', args=[str(self.id)])

class Comment(models.Model):
    article = models.ForeignKey(Article, on_delete=models.CASCADE, related_name='comments')
    body = models.TextField()
    author = models.ForeignKey(User, on_delete=models.CASCADE)
    created_at = models.DateTimeField(auto_now_add=True)

    def __str__(self):
        return f"Comment by {self.author} on {self.article}"
```

---

## ✅ 4. Make and Apply Migrations

```bash
python manage.py makemigrations
python manage.py migrate
```

---

## ✅ 5. Create Admin Access

### In `news/admin.py`

```python
from django.contrib import admin
from .models import Article, Comment

admin.site.register(Article)
admin.site.register(Comment)
```

---

## ✅ 6. Create Forms

### `news/forms.py`

```python
from django import forms
from .models import Article, Comment

class ArticleForm(forms.ModelForm):
    class Meta:
        model = Article
        fields = ['title', 'body']

class CommentForm(forms.ModelForm):
    class Meta:
        model = Comment
        fields = ['body']
```

---

## ✅ 7. Create Views

### `news/views.py`

```python
from django.shortcuts import render, get_object_or_404, redirect
from django.contrib.auth.decorators import login_required
from django.http import HttpResponseForbidden
from .models import Article
from .forms import ArticleForm, CommentForm

def article_list(request):
    articles = Article.objects.all().order_by('-created_at')
    return render(request, 'news/article_list.html', {'articles': articles})

def article_detail(request, pk):
    article = get_object_or_404(Article, pk=pk)
    comments = article.comments.all()
    
    if request.method == "POST":
        form = CommentForm(request.POST)
        if form.is_valid():
            new_comment = form.save(commit=False)
            new_comment.article = article
            new_comment.author = request.user
            new_comment.save()
            return redirect('article_detail', pk=pk)
    else:
        form = CommentForm()

    return render(request, 'news/article_detail.html', {
        'article': article,
        'comments': comments,
        'form': form
    })

@login_required
def article_create(request):
    if request.method == 'POST':
        form = ArticleForm(request.POST)
        if form.is_valid():
            new_article = form.save(commit=False)
            new_article.author = request.user
            new_article.save()
            return redirect('article_detail', pk=new_article.pk)
    else:
        form = ArticleForm()
    return render(request, 'news/article_form.html', {'form': form})

@login_required
def article_edit(request, pk):
    article = get_object_or_404(Article, pk=pk)
    if article.author != request.user:
        return HttpResponseForbidden("You are not allowed to edit this article.")
    
    if request.method == 'POST':
        form = ArticleForm(request.POST, instance=article)
        if form.is_valid():
            form.save()
            return redirect('article_detail', pk=pk)
    else:
        form = ArticleForm(instance=article)
    return render(request, 'news/article_form.html', {'form': form})

@login_required
def article_delete(request, pk):
    article = get_object_or_404(Article, pk=pk)
    if article.author != request.user:
        return HttpResponseForbidden("You are not allowed to delete this article.")
    
    if request.method == 'POST':
        article.delete()
        return redirect('article_list')
    
    return render(request, 'news/article_confirm_delete.html', {'article': article})
```

---

## ✅ 8. Set Up URLs

### `news/urls.py`

```python
from django.urls import path
from . import views

urlpatterns = [
    path('', views.article_list, name='article_list'),
    path('article/<int:pk>/', views.article_detail, name='article_detail'),
    path('article/new/', views.article_create, name='article_create'),
    path('article/<int:pk>/edit/', views.article_edit, name='article_edit'),
    path('article/<int:pk>/delete/', views.article_delete, name='article_delete'),
]
```

### `newsreader/urls.py`

```python
from django.contrib import admin
from django.urls import path, include
from django.contrib.auth import views as auth_views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('accounts/login/', auth_views.LoginView.as_view(), name='login'),
    path('accounts/logout/', auth_views.LogoutView.as_view(next_page='/'), name='logout'),
    path('', include('news.urls')),
]
```

---

## ✅ 9. Templates

Create template files:

### `templates/news/article_list.html`

```html
<h1>Articles</h1>
{% for article in articles %}
    <h2><a href="{% url 'article_detail' article.pk %}">{{ article.title }}</a></h2>
    <p>by {{ article.author }} | {{ article.created_at }}</p>
{% endfor %}
<a href="{% url 'article_create' %}">Write a New Article</a>
```

### `templates/news/article_detail.html`

```html
<h1>{{ article.title }}</h1>
<p>{{ article.body }}</p>
<p>by {{ article.author }}</p>

{% if request.user == article.author %}
    <a href="{% url 'article_edit' article.pk %}">Edit</a>
    <form method="post" action="{% url 'article_delete' article.pk %}">
        {% csrf_token %}
        <button type="submit">Delete</button>
    </form>
{% endif %}

<h2>Comments</h2>
{% for comment in comments %}
    <p><strong>{{ comment.author }}</strong>: {{ comment.body }}</p>
{% endfor %}

{% if request.user.is_authenticated %}
<form method="post">
    {% csrf_token %}
    {{ form.as_p }}
    <button type="submit">Add Comment</button>
</form>
{% else %}
<p><a href="{% url 'login' %}">Login</a> to comment.</p>
{% endif %}
```

### `templates/news/article_form.html`

```html
<h1>New / Edit Article</h1>
<form method="post">
    {% csrf_token %}
    {{ form.as_p }}
    <button type="submit">Save</button>
</form>
```

### `templates/news/article_confirm_delete.html`

```html
<h1>Are you sure you want to delete "{{ article.title }}"?</h1>
<form method="post">
    {% csrf_token %}
    <button type="submit">Yes, delete</button>
</form>
<a href="{% url 'article_detail' article.pk %}">Cancel</a>
```

---

## ✅ 10. Create Superuser & Run Server

```bash
python manage.py createsuperuser
python manage.py runserver
```

Visit: [http://127.0.0.1:8000](http://127.0.0.1:8000)

---

## ✅ Next Steps

* [ ] Add tags or categories
* [ ] Use class-based views
* [ ] Add pagination
* [ ] Use Markdown for formatting

Would you like this bundled into a downloadable zip, or want to host it on GitHub later?







---

#  Chapter 7: User Authentication and password management

- To learn about basic authentication system  we'll integrate the following into our blog app:

* **User Login**
* **User Logout**
* **User signup**
  

---

## 1. Update `settings.py`

Add this to the **bottom** of `myblog/settings.py`:

python
```
# Redirect after login/logout
LOGIN_REDIRECT_URL = '/'
LOGOUT_REDIRECT_URL = '/'
```

---

##  2. Add Auth URLs to Main `urls.py`

In `myblog/urls.py`, import Django’s auth views and add paths:

python
```

from django.contrib import admin
from django.urls import path, include
from django.contrib.auth import views as auth_views
from django.contrib.auth.views import LogoutView

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('blog.urls')),
    path('login/', auth_views.LoginView.as_view(template_name='blog/login.html'), name='login'),
    path('logout/', auth_views.LogoutView.as_view(), name='logout'),
    path('logout/', LogoutView.as_view(), name='logout'),
]

```

---

## 3. Add Registration URL
In blog/urls.py:

python
```
from . import views

urlpatterns = [
    path('', views.home, name='blog-home'),
    path('add/', views.create_post, name='create-post'),
    path('register/', views.register, name='register'),
]

```

---

##  4. Protect "Add Post" View (Login Required)

Update view in `blog/views.py` to require login and signup:

python
```
from django.shortcuts import render, redirect
from .models import Post
from .forms import PostForm
from django.contrib.auth.decorators import login_required
from django.contrib.auth import login
from django.contrib.auth.forms import AuthenticationForm
from .forms import RegisterForm

def home(request):
    posts = Post.objects.all()
    return render(request, 'blog/home.html', {'posts': posts})


def register(request):
    if request.method == 'POST':
        form = RegisterForm(request.POST)
        if form.is_valid():
            user = form.save()
            login(request, user)  # Automatically log in new user
            return redirect('blog-home')
    else:
        form = RegisterForm()
    return render(request, 'blog/register.html', {'form': form})


@login_required

def create_post(request):
    if request.method == 'POST':
        form = PostForm(request.POST)
        if form.is_valid():
            form.save()
            return redirect('blog-home')
    else:
        form = PostForm()
    return render(request, 'blog/create_post.html', {'form': form})


```

---


##  5. Create a Registration Form
In blog/forms.py, add a registration form using Django's built-in UserCreationForm:

 ```
from django import forms
from .models import Post
from django.contrib.auth.forms import UserCreationForm
from django.contrib.auth.models import User


class PostForm(forms.ModelForm):
    class Meta:
        model = Post
        fields = ['title', 'content', 'author']


class RegisterForm(UserCreationForm):
    email = forms.EmailField(required=True)
    class Meta:
        model = User
        fields = ['username', 'email', 'password1', 'password2']

 ```


##  6. Show Login/Logout and signup in Navbar 

Update `blog/templates/blog/home.html` to show login/logout and signup:
html
```
<!DOCTYPE html>
<html>
<head>
    <title>Blog Home</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 40px;
            background-color: #f9f9f9;
            
        }

        h1 {
            color: #333;
            margin-bottom: 20px;
        }

        .post {
            background: #fff;
            border: 1px solid #ddd;
            padding: 20px;
            margin-bottom: 20px;
            border-radius: 8px;
        }

        .post h2 {
            margin: 0;
            color: #2c3e50;
        }

        .post small {
            color: #888;
        }

        a.button {
            display: inline-block;
            padding: 10px 15px;
            background-color: #007bff;
            color: white;
            text-decoration: none;
            border-radius: 4px;
            margin-bottom: 20px;
        }

        a.button:hover {
            background-color: #0056b3;
        }


    </style>
</head>
<body>
        <h1>Blog Posts</h1>

   {% if user.is_authenticated %}
    <p>Welcome, {{ user.username }}! 
    <form method="post" action="{% url 'logout' %}">
    {% csrf_token %}
    <button type="submit">Logout</button>
    </form>
{% else %}
    <a href="{% url 'login' %}" class="button">Login</a><br>
    <a href="{% url 'register' %}" class="button" style="background-color: #4947a8;">Register</a>
    
{% endif %}

    <hr>
    
    {% for post in posts %}
        <div class="post">
            <h2>{{ post.title }}</h2>
            <p>{{ post.content }}</p>
            <small>By {{ post.author }} on {{ post.date_posted }}</small>
        </div>
    {% empty %}
        <p>No posts yet.</p>
    {% endfor %}
</body>
</html>

```

---
---
##  3. Create Login Template

**Path:** `blog/templates/blog/login.html`

html
```
<!DOCTYPE html>
<html>
<head>
    <title>Login</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 40px;
            background-color: #f4f4f4;
        }

        form {
            background: #fff;
            padding: 25px;
            border: 1px solid #ddd;
            border-radius: 8px;
            max-width: 400px;
        }

        button {
            padding: 10px 15px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 4px;
        }

        a {
            margin-top: 15px;
            display: inline-block;
        }
    </style>
</head>
<body>
    <h1>Login</h1>

    <form method="post">
        {% csrf_token %}
        {{ form.as_p }}
        <button type="submit">Log in</button>
    </form>
</body>
</html>
```
---

## 6. Create a sign up templates:

```
<!DOCTYPE html>
<html>
<head>
    <title>Register</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 40px;
            background-color: #f4f4f4;
        }

        form {
            background: #fff;
            padding: 25px;
            border: 1px solid #ddd;
            border-radius: 8px;
            max-width: 400px;
        }

        button {
            padding: 10px 15px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 4px;
        }

        a {
            margin-top: 15px;
            display: inline-block;
        }
    </style>
</head>
<body>
    <h1>Register</h1>

    <form method="post">
        {% csrf_token %}
        {{ form.as_p }}
        <button type="submit">Sign Up</button>
    </form>

    <a href="{% url 'login' %}">Already have an account? Log in</a><br>
    <a href="{% url 'blog-home' %}">← Back to Home</a>
</body>
</html>

```

---
##  6. Create a User to Test
bash
```
python manage.py createsuperuser
```
try and test the webpage you have created

##  Structure of blog app after adding all the above given features

![image](https://github.com/user-attachments/assets/03f6cad0-50f4-46c2-86cf-519a6aff12be)

 ---


## To learn about more clear flow of authentication and password management we will intergerate the following features into our pre existing Newspaper app in chapter 6.All using custom templates/pages, not the default Django ones,

* **User signup**
* **Login**
* **Logout**
* **Password change**
* **Password reset**


---

##  Step 1: Project Setup

### 1.1 Ensure your app is ready

If you haven’t created the app:

bash

```
python manage.py startapp accounts
```

### 1.2 Add `accounts` to `INSTALLED_APPS` in `settings.py`:

python

```
INSTALLED_APPS = [
    ...
    'accounts',
    'django.contrib.auth',
    'django.contrib.messages',
    ...
]
```

### 1.3 Configure `TEMPLATES` and `STATICFILES_DIRS` if needed:

Ensure your `TEMPLATES` setting looks like this:

python

```
TEMPLATES = [
    {
        ...
        'DIRS': [BASE_DIR / 'templates'],  # global templates dir
        ...
    },
]
```

---

## ✅ Step 2: Create URLs

### 2.1 In `accounts/urls.py`:

python

```
from django.urls import path
from . import views
from django.contrib.auth import views as auth_views

urlpatterns = [
    path('signup/', views.signup_view, name='signup'),
    path('login/', auth_views.LoginView.as_view(template_name='accounts/login.html'), name='login'),
    path('logout/', auth_views.LogoutView.as_view(template_name='accounts/logout.html'), name='logout'),
    path('password_change/', auth_views.PasswordChangeView.as_view(template_name='accounts/password_change.html'), name='password_change'),
    path('password_change/done/', auth_views.PasswordChangeDoneView.as_view(template_name='accounts/password_change_done.html'), name='password_change_done'),
    path('password_reset/', auth_views.PasswordResetView.as_view(template_name='accounts/password_reset.html'), name='password_reset'),
    path('password_reset/done/', auth_views.PasswordResetDoneView.as_view(template_name='accounts/password_reset_done.html'), name='password_reset_done'),
    path('reset/<uidb64>/<token>/', auth_views.PasswordResetConfirmView.as_view(template_name='accounts/password_reset_confirm.html'), name='password_reset_confirm'),
    path('reset/done/', auth_views.PasswordResetCompleteView.as_view(template_name='accounts/password_reset_complete.html'), name='password_reset_complete'),
]
```

### 2.2 Include `accounts.urls` in your project’s `urls.py`:

python

```
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('accounts/', include('accounts.urls')),
]
```

---

## ✅ Step 3: Create Signup View

### 3.1 In `accounts/views.py`:

python

```
from django.contrib.auth.forms import UserCreationForm
from django.shortcuts import render, redirect

def signup_view(request):
    if request.method == 'POST':
        form = UserCreationForm(request.POST)
        if form.is_valid():
            form.save()
            return redirect('login')
    else:
        form = UserCreationForm()
    return render(request, 'accounts/signup.html', {'form': form})
```

---

## ✅ Step 4: Create Templates

Create the following files in: `templates/accounts/`
(e.g., `myproject/templates/accounts/login.html`, etc.)

### 4.1 Base layout (`templates/base.html`)

html

```
<!DOCTYPE html>
<html>
<head>
    <title>NewsReader Auth</title>
</head>
<body>
    <nav>
        <a href="{% url 'signup' %}">Sign Up</a> |
        <a href="{% url 'login' %}">Login</a> |
        <a href="{% url 'logout' %}">Logout</a> |
        <a href="{% url 'password_change' %}">Change Password</a> |
        <a href="{% url 'password_reset' %}">Reset Password</a>
    </nav>
    <hr>
    {% if messages %}
        {% for message in messages %}
            <p>{{ message }}</p>
        {% endfor %}
    {% endif %}
    {% block content %}{% endblock %}
</body>
</html>
```

### 4.2 Signup (`signup.html`)

html

```
{% extends "base.html" %}
{% block content %}
<h2>Sign Up</h2>
<form method="post">
    {% csrf_token %}
    {{ form.as_p }}
    <button type="submit">Sign Up</button>
</form>
{% endblock %}
```

### 4.3 Login (`login.html`)

html

```
{% extends "base.html" %}
{% block content %}
<h2>Login</h2>
<form method="post">
    {% csrf_token %}
    {{ form.as_p }}
    <button type="submit">Login</button>
</form>
{% endblock %}
```

### 4.4 Logout (`logout.html`)

html

```
{% extends "base.html" %}
{% block content %}
<h2>You have been logged out.</h2>
<a href="{% url 'login' %}">Log in again</a>
{% endblock %}
```

### 4.5 Password Change & Done

**password\_change.html**

html

```
{% extends "base.html" %}
{% block content %}
<h2>Change Password</h2>
<form method="post">
    {% csrf_token %}
    {{ form.as_p }}
    <button type="submit">Change</button>
</form>
{% endblock %}
```

**password\_change\_done.html**

html

```
{% extends "base.html" %}
{% block content %}
<p>Password changed successfully.</p>
{% endblock %}
```

### 4.6 Password Reset

**password\_reset.html**

html

```
{% extends "base.html" %}
{% block content %}
<h2>Reset Your Password</h2>
<form method="post">
    {% csrf_token %}
    {{ form.as_p }}
    <button type="submit">Send Reset Email</button>
</form>
{% endblock %}
```

**password\_reset\_done.html**

html

```
{% extends "base.html" %}
{% block content %}
<p>Check your email for the reset link.</p>
{% endblock %}
```

**password\_reset\_confirm.html**

html

```
{% extends "base.html" %}
{% block content %}
<h2>Enter new password</h2>
<form method="post">
    {% csrf_token %}
    {{ form.as_p }}
    <button type="submit">Change password</button>
</form>
{% endblock %}
```

**password\_reset\_complete.html**

html

```
{% extends "base.html" %}
{% block content %}
<p>Your password has been reset. <a href="{% url 'login' %}">Login</a></p>
{% endblock %}
```

---

## ✅ Step 5: Email Settings for Reset

Add to `settings.py` (use console backend for dev):

python

```
EMAIL_BACKEND = 'django.core.mail.backends.console.EmailBackend'
```

---

## ✅ Step 6: Migrate & Run

bash

```
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

Visit `http://127.0.0.1:8000/accounts/signup/` to start testing.

---
