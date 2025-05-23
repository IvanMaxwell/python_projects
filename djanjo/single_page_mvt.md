# Django Single Page Login App

- A minimalist Django web application that loads a single login page at the root URL (`/`).

- Useful as a boilerplate for beginners learning Django's structure and routing.

- Perfect for beginners learning Django’s **MVT (Model-View-Template)** architecture or for setting up a base login UI to extend with authentication.

**What Is Django?**

- Django is a tool (framework) that helps you build websites and web applications using the Python programming language.

- Think of Django like Lego blocks — it gives you pieces that you can combine to make websites faster and more securely


**What is git bash**

- It's is an application for Microsoft Windows environments which provides an emulation layer for a Git command line experience

- Bash is an acronym for Bourne Again Shell. A shell is a terminal application used to interface with an operating system through written commands.


**Features**

- Django 5+ compatible  
- Simple and clean login form  
- Easy project structure  
- Great starting point for adding authentication  


**Tech Stack**
- Python 3.10+  
- Django 5.x  
- HTML5, CSS (customizable)



# Here is a step by step process:

Note:

- The bash means the git bash we installed and we can also give the command in terminal in vscode
- python means the python code file in the structure
- html means the html code file in stucture
  
# Setup Instructions

**-  Install Python and Django**

- Before you start, make sure Python is installed on your computer.

- Check Python:
Open your terminal or command prompt and type:
```
In bash
python --version
```
- If Python is installed, it will show a version like Python 3.10.x.

- If not,https://www.python.org/downloads/windows/

- If the python isn't available in the terminal then, 

- go check path, here are the steps to do,

**step1;** Go to Start and enter advanced system settings in the search bar.

**step2;** Click View advanced system settings.

**step3;** In the System Properties dialog, click the Advanced tab and then click Environment Variables.

**Depending on your installation:**

**case1:**

- If you selected Install for all users during installation, select Path from the list of System Variables and click Edit.

**case2:**


- If you didn’t select Install for all users during installation, select Path from the list of User Variables and click Edit.
Click New and enter the Python directory path, then click OK until all the dialogs are closed.

**Step 4 ;** Verify the Python Installation


- You can verify whether the Python installation is successful either through the command line or through the Integrated Development Environment (IDLE) application, if you chose to install it.

- Go to Start and enter cmd in the search bar. Click Command Prompt.

**Enter the following command in the command prompt:**

```
In bash or terminal in vscode
python --version
```
for more referance on how to install python refer this web, https://www.digitalocean.com/community/tutorials/install-python-windows-10

- install django
  
- bash
```
pip install django

```
# Starting the project

**🔹 1.Create Django Project and App**

If you're starting from scratch:

- bash
```
django-admin startproject login_project .     #Creates a new Django project named login_project,we can also change the project name
python manage.py startapp login_app     #Creates a Django app called login_app,also name changeable
```

**🔹 2.Configure the Project**

1. Enable the app in
  
 **login_project/settings.py**

- Find the INSTALLED_APPS section and add 'login_app',:

python
```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'login_app',  # ✅ Add this line,without it Django won’t recognize your app Without it, things like models, admin pages, templates, and signals won’t work properly.


]
```

2. Configure templates directory,
   
- In the same settings.py, find the TEMPLATES section and update 'DIRS' like this:

- 'DIRS' tells Django:"Look in these directories for templates"

python
```
import os

TEMPLATES = [
    {
        ...
        'DIRS': [os.path.join(BASE_DIR, 'login_app', 'templates')],   #Safely builds the full path to your templates folder
        ...
    },
]
```

**🔹 3. Set Up URLs**

Inside,

**login_project/urls.py**

- python
```
from django.contrib import admin
from django.urls import path, include  #path:Lets you define URL patterns ,include: Lets you import URL patterns from another file



urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('login_app.urls')),  # 'login_app.urls' is the location of your app-specific URL patterns.


]

```
- now again in login_app/urls.py ,add the following line
  python
  ```
  path('',views.login_view,name='login'),
  ```
  - It should look like the following,
- python
```
from django.urls import path
from . import views

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('login_app.urls'))
    path('', views.login_view, name='login'),    #Calls your login page rendering function and Allows you to refer to this route by name in templates and redirects

]
```

**🔹 5. Create the View**
- In login_app/views.py

- python
```
from django.shortcuts import render

def login_view(request):    #defines a function-based view, request is an object that contains all the details of the current HTTP request
    return render(request, 'login.html')  #Tells Django to render a template named 'login.html' and Sends that HTML back to the user's browser
```

**🔹 6. Create the Template**
- login_app/templates/login.html

- html
```
<!DOCTYPE html>
<html>
<head>
    <title>Login</title>
</head>
<body>
    <h2>Login Page</h2>
    <form method="post">
        {% csrf_token %}
        <label>Username:</label><br>
        <input type="text" name="username"><br><br>

        <label>Password:</label><br>
        <input type="password" name="password"><br><br>

        <button type="submit">Login</button>
    </form>
</body>
</html>
```
Note: if you want to add css to file here is an inline line css file 

- inside head tag add the following
- 
```
      <style>
        body {
            font-family: Arial, sans-serif;
            background: #f0f2f5;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        form {
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            width: 300px;
            position: relative;
            right: 259px;
        }

        h2 {
            display: inline;
            font-size: 3rem;
            font-style:oblique;
            margin-bottom: 20px;
            color: #333;
            position:relative;
            bottom:220px;
            left: 50px;
        }

        label {
            font-weight: bold;
            display: flex;
            justify-content: center;
            margin-top: 10px;
            color: #555;

        }

        input[type="text"],
        input[type="password"] {
            width: 100%;
            padding: 8px;
            margin-top: 5px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        button {
            width: 100%;
            padding: 10px;
            margin-top: 20px;
            background: #007bff;
            color: white;
            border: none;
            border-radius: 5px;
            font-weight: bold;
            cursor: pointer;
        }

        button:hover {
            background: #0056b3;
        }
    </style>
```


**🔹 7. Run Migrations**
- bash
```
python manage.py makemigrations         
python manage.py migrate            #Scans your app's models.py file for any new or changed database models.Creates a migration file (a Python script) that describes how to apply those changes to the database.
```

**🔹 8. Run the Server**

- bash
```
python manage.py runserver           #tells python to start running the server 
```


**Visit:**
👉 http://127.0.0.1:8000/

You should see your login page!


  


**📌 Notes**
- No login logic (like authentication) is implemented — just a static form.

- Extend it by integrating Django's built-in User model and authentication views.


# Author

**IvanMaxwell**

**GitHub**


