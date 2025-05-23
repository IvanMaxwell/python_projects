# Chapter 1: Initial Set Up of Django
 
 - This chapter covers how to properly configure your computer to work on Django projects.
 
 - We start with an overview of the command line and how to install the latest version of Django and Python.
 
 - Then we discuss virtual environments, git, and working with a text editor.
 
 - By the end of this chapter you’ll be ready to create and modify new Django projects in just a few keystrokes.

 - Before we explore about Django we need to know about some general inforamation,

# What is Django?

- Django is a high-level Python web framework that enables rapid development of secure and maintainable websites.

 - It encourages clean, pragmatic design and follows the "Don't Repeat Yourself" (DRY) principle.

 - 2003: Created by developers at the Lawrence Journal-World newspaper to manage news content.
  
 - 2005: Open-sourced and named after jazz guitarist Django Reinhardt.
  
 - Now maintained by the Django Software Foundation, it is one of the most popular web frameworks for Python.


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



| Command      | Description                 |
| ------------ | --------------------------- |
| `cd`         | Navigate into a directory   |
| `cd ..`      | Move up one directory       |
| `ls` / `dir` | List files (Mac / Windows)  |
| `pwd`        | Show current directory path |
| `mkdir`      | Create a new directory      |
| `touch`      | Create a new file on mac      |




# How to install django:

**Installing Python**

Python is required for Django development.

Follow the steps below to install it on your system.

For macOS
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

For Windows,

Download Python from the official site:

https://www.python.org/downloads/windows/

Run the installer:

Make sure to check the box that says "Add Python to PATH"

For Linux

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




# installation of django

 
1. Make sure Python is already installed in our system for django
 
python --version 
 
2. Install django by using pip 
 
pip install django 
pip install django == 1.11.9 
 
D:\>pip install django 
Collecting django 
Downloading  
https://files.pythonhosted.org/packages/51/1a/6153103322/Django-2.1-py3-none
any.whl (7.3MB) 100% || 7.3MB 47kB/s 
 
Collecting pytz (from django) 
  Downloading https://files.pythonhosted.org/packages/30/4e/ 
53b898779a/pytz-2018.5-py2.py3-none-any.whl (510kB) 
    100% || 512kB 596kB/s 
 
Installing collected packages: pytz, django 
Successfully installed django-2.1 pytz-2018.5 
You are using pip version 9.0.3, however version 18.0 is ava 
You should consider upgrading via the 'python -m pip install 
 
3. To check django version: 
 
py -m django --version
