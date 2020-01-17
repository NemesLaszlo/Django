# Django
Python - Django Practise and Learning.

#### What is Django

Django is a very popular and widely used full stack web development framework for python. 
It is used by large companies like Instagram and pintrest! 
The main advantage of django is that you program almost everything using only python.

#### Install

Django is a python module and can be installed via pip. 
Simply open your command prompt or terminal and type "pip install django".

#### Setting up a Project

The first thing we need to do when we want to start using django is setup a project. 
To do this we will need to create a directory somewhere to store our django project.
Once we've done that we will need to open our command prompt and change into that directory.
Now we will type the following into cmd or terminal: "django-admin startproject " and the name of our project.

Next we will change directories again into the name of our project. 
Once we've done this we can test that our installation was successful by running the command "python manage.py runserver" 
and going to the highlighted url in our web browser.

##### If you are successfully able to connect to the url then you are all done setting up a django project!

#### Creating an App

Now that we have created a django project we need to create a django app. 
An app is what will have pages and views and represent your site. 
Whereas the project is kind of an environment that runs your app!( Note that you can multiple apps within one django project. )

To create an app make sure you are in the same directory as the manage.py file and type the following: "python manage.pt startapp "

#### Creating a View

Now that we've created an app we can start modifying some files within our app to create our first web page (aka view).

To do this we will go into our apps root directory and modify the file called views.py.

Now that we've created a view we need to create a url to link to it.
To do this we need to create a new python file called urls.py. 
This file will be in root directory of our app (same place as views.py).
