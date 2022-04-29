# Introduction

Here we will see commands used to create the project, make migrations, admin area end much more

---

## Django start project

The command to create a new project is:

```py

django-admin startproject nameproj

```

It will create a folder with a project inside, and also will be create a file called manage.py, and that file will be important to use commands of Django system.

## Create a app

To create a app we will use this command:

```py
python manage.py startapp nameapp
```

This command will create another folder containing files to create views, models and routes.

In the file settings.py we will add on `INSTALLED_APPS` the name of the app that we already created.

## Models

In the second folder, we have the file `models.py` where we will create the DB tables using python syntax.

```py

class Color(models.Model):
    namecolor = models.CharField(max_length=200, null=False)
pass

```

```py
class People(models.Model):
    name = models.CharField(max_length=100, null=False)
    email = models.EmailField()
    id_colors = models.ForeignKey(Cores, on_delete=models.CASCADE)
pass

```

## Create migration

To create a migration we will use this command:

```py
python manage.py makemigrations

```

and then that:

```py
python manage.py sqlmigrate dbconex 0001

```

0001 was a file created inside the migrations folder, and then:

```py
python manage.py migrate
```

## Run the server

To run the server we will use this command:

```py
python manage.py runserver

```

and it will show us which port is running

## Admin area


## API django


## Template engine Jinja2

## Static files

We will add on the file settings.py the path to the static files:

```py
STATICFILES_DIRS = [
BASE_DIR / "static",
]
```

> the static folder must be created in the root of the project