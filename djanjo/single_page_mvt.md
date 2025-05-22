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
django-admin startproject login_project .
python manage.py startapp login_app
```

**🔹 3.Configure the Project**
3.1. Enable the app in login_project/settings.py
Find the INSTALLED_APPS section and add 'login_app',:

python
```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'login_app',  # ✅ Add this line
]
```
3.2. Configure templates directory
In the same settings.py, find the TEMPLATES section and update 'DIRS' like this:

python
Copy
Edit
import os

TEMPLATES = [
    {
        ...
        'DIRS': [os.path.join(BASE_DIR, 'login_app', 'templates')],
        ...
    },
]

**🔹 4. Set Up URLs**

- login_project/urls.py

- python
```
from django.contrib import admin
from django.urls import path, include  # ✅ include is important

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('login_app.urls')),  # root URL to login_app
]

```
- login_app/urls.py
- python
```
from django.urls import path
from . import views

urlpatterns = [
    path('', views.login_view, name='login'),
]
```

**🔹 5. Create the View**
- login_app/views.py

- python
```
from django.shortcuts import render

def login_view(request):
    return render(request, 'login.html')
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
python manage.py migrate
```

**🔹 8. Run the Server**

- bash
```
python manage.py runserver
```


**Visit:**
👉 http://127.0.0.1:8000/

You should see your login page!


  


**📌 Notes**
- No login logic (like authentication) is implemented — just a static form.

- Extend it by integrating Django's built-in User model and authentication views.


**Author
IvanMaxwell
GitHub**


