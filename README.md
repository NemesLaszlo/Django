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

### Database Setup (SQLIte3)

##### Modifying settings.py

The first step to setting up our database is to tell django that we have added an application to our project and that it requires some setup. To do this we need to navigate to the settings.py file from within our interior site directory and add the following line to the installed apps section: 'main.apps.MainConfig', If you've named your application something other than main you will need to replace "main" and "Main" with the name of your application.

##### Migrations

Django has it's own version control system that is called migrations. Similar to GIT when you make a change that requires any new dependencies to be installed you need to tell django from the command line. Each change you make will be logged as a migration and can be viewed afterwards to allow you to revert to previous versions.

To tell django to start setting up our database use the following command (make sure you are in the directory containing manage.py).
python manage.py migrate

##### Defining Models

Now that we have setup our database we need to define some models for storing information. To do this navigate to the models.py from inside our application folder.

When we define a model we simply create a class that is the name of our model that inherits from models.Model. Then we define all of the fields or attributes of our model as class variables. We can also add methods to use on our models.

##### Making Migrations

Now that we've updated our models file we need to tell django to make changes to our database. To do this we use the following command:
python manage.py makemigrations main. If your app is named something else replace "main" with its name.

Finally to apply the migrations we use:
python manage.py migrate

##### Working With Our Database

Now that we've defined some models we can start adding information to our database. The commands shown below were executed in a python shell, however they can be used from your python files in the same/similar ways.

```python
from main.models import Item, ToDoList # import will be different depending on script location

list1 = ToDoList(name="Leslie's List")  # create a ToDoList

list1.save()  # saves the ToDoList in the database

print(list1.id)  # prints 1, each list is given an id automatically

print(ToDoList.objects.all())  # prints all of the ToDoLists in the database

find_list = ToDoList.objects.get(name="Leslie's list")  # gets the ToDoList object(s) with name "Leslie's List"

# Since we defined a relationship between Item and ToDoList each ToDoList has an "item_set"

print(list1.item_set.all())  # get all of the items on a ToDoList

list1.create(text="Go to the mall", complete=False)  # add an item to the ToDoList

list1.name = "new name"  # change the name of the list

list1.save()  # save changes

list1.delete()  # delete the list
```

### Creating an Admin Login

If you navigate to the django admin page you will notice that it asks you for some login information. However, right now we have no login. To create a login we need to navigate to the directory containing migrate.py and run the following command: python manage.py createsuperuser

Once you have created a user run the server by running python manage.py runserver and navigate to the "admin/" address. Here you can use your login information to login.

### Adding Our Database

This page is meant to show us (the admin) information about our site and database. To add our database to this dashboard we need to modify the admin.py file from within our app directory.
