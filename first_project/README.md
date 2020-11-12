# FIRST_PROJECT
## Project Creation
to create a project in Django you will need to run:
```
django-admin startproject name_project
```
once you run the above command you will see there are these files inside
the project directory
- manage.py:  This is a command-line utility used to interact with your project.
It is a thin wrapper around the django-admin.py tool. You don't need to edit
this file.
- init.py: An empty file that tells Python to treat the mysite
directory as a Python module.
- asgi.py: This is the configuration to run your project as ASGI,
the emerging Python standard for asynchronous web servers and
applications.
- wsgi.py: This is the configuration to run your project as a Web
Server Gateway Interface (WSGI) application
- settings.py: This indicates settings and configuration for your
project and contains initial default settings. Here you will find Database configuration
midleware, security and more configurations
- urls.py: This is the place where your URL patterns live. Each URL
defined here is mapped to a view.

## Migrate installed_apps
To complete the project setup, you
need to create the tables associated with the models of the applications listed in
INSTALLED_APPS(settings.py).
```
python manage.py migrate
```
after doing the migrate part now, you will be able to run your development server
```
python manage.py runserver
or
python manage.py runserver 8001
```
once you run the above code you should see a page
stating that the project is successfully running.<br>
<br>

Remember that this server is only intended for development and is not suitable
for production use. In order to deploy Django in a production environment, you
should run it as a WSGI application using a web server, such as Apache, Gunicorn,
or uWSGI, or as an ASGI application using a server like Uvicorn or Daphne.

## Settings
settings.py is an important file on which you will find
* DEBUG is a Boolean that turns the debug mode of the project on and off. If it
is set to True, Django will display detailed error pages when an uncaught
exception is thrown by your application. When you move to a production
environment, remember that you have to set it to False. Never deploy a
site into production with DEBUG turned on because you will expose sensitive
project-related data.

* ALLOWED_HOSTS is not applied while debug mode is on or when the tests
are run. Once you move your site to production and set DEBUG to False,
you will have to add your domain/host to this setting in order to allow it
to serve your Django site.

* INSTALLED_APPS is a setting you will have to edit for all projects. This
setting tells Django which applications are active for this site. By default,
Django includes the following applications:
* * django.contrib.admin: An administration site
* * django.contrib.auth: An authentication framework
* * django.contrib.contenttypes: A framework for handling
content types
* * django.contrib.sessions: A session framework
* * django.contrib.messages: A messaging framework
* * django.contrib.staticfiles: A framework for managing static
files
* MIDDLEWARE is a list that contains middleware to be executed.
* ROOT_URLCONF indicates the Python module where the root URL patterns
of your application are defined.
* DATABASES is a dictionary that contains the settings for all the databases to
be used in the project. There must always be a default database. The default
configuration uses an SQLite3 database.
* LANGUAGE_CODE defines the default language code for this Django site.
* USE_TZ tells Django to activate/deactivate timezone support. Django comes
with support for timezone-aware datetime. This setting is set to True when
you create a new project using the startproject management command.

## App creation
Inside a Django project you will can create a lot of applications, you arent restricted to one,
of course it depends on your web application and you imagination.<br>
But it is recommended to create more than just one app inside your project.

```
python manage.py startapp name_app
```
once you create your app, inside of you app directory you should find:
* admin.py: This is where you register models to include them in the Django
administration site—using this site is optional.
* apps.py: This includes the main configuration of your application.
* migrations: This directory will contain database migrations of your
application. Migrations allow Django to track your model changes and
synchronize the database accordingly.
* models.py: This includes the data models of your application; all Django
applications need to have a models.py file, but this file can be left empty.
* tests.py: This is where you can add tests for your application.
* views.py: The logic of your application goes here; each view receives an
HTTP request, processes it, and returns a response (this file works as the controller).
