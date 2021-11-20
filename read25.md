# [reading-note-401](https://mohammadsilwadi.github.io/reading-note-401/)
## Docker
### What is Docker and why it is used?
Docker is an open source containerization platform. It enables developers to package applications into containers—standardized executable components combining application source code with the operating system (OS) libraries and dependencies required to run that code in any environment.


### Docker is a way to run Linux containers
+ Containers are a lightweight alternative to Virtual Machines
+ Dockerfile is a list of instructions for creating an image
+ Images are made up of one or more layers
+ Containers are a running instance of an image
+ docker-compose.yml controls how to run the container
+ Containers are stateless and ephemeral in nature. We can link the local filesystem via volumes but things become more complex with databases .

## Library Website and API
Django REST Framework works alongside the Django web framework to create web APIs. 
We cannot build a web API with only Django Rest Framework; it always must be added to a project after Django itself has been installed and configured.

### Django REST Framework

Django REST Framework is added just like any other third-party app. Make sure to quit the local server Control + c if it is still running. Then on the command line type the below.
```
(library) $ pipenv install djangorestframework~=3.11.0
```
Add it to the INSTALLED_APPS config in our settings.py file. I like to make a distinction between third-party apps and local apps as follows since the number of apps grows quickly in most projects.

### config/settings.py
```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',

    # 3rd party
    'rest_framework', # new

    # Local
    'books',
]

```

Ultimately, our API will expose a single endpoint that lists out all books in JSON. So we will need a new URL route, a new view, and a new serializer file (more on this shortly).

There are multiple ways we can organize these files however my preferred approach is to create a dedicated api app. That way even if we add more apps in the future, each app can contain the models, views, templates, and urls needed for dedicated webpages, but all API-specific files for the entire project will live in a dedicated api app.

Let’s first create a new api app.

Then add it to INSTALLED_APPS

The api app will not have its own database models so there is no need to create a migration file and run migrate to update the database.

### urls 
Let’s start with our URL configs. Adding an API endpoint is just like configuring a traditional Django app’s routes. First at the project-level we need to include the api app and configure its URL route, which will be api/


create a urls.py file within the api app

### Views

Next up is our views.py file which relies on Django REST Framework’s built-in generic class views. These deliberately mimic traditional Django’s generic class-based views in format, but they are not the same thing.

To avoid confusion, some developers will call an API views file apiviews.py or api.py. Personally, when working within a dedicated api app I do not find it confusing to just call a Django REST Framework views file views.py but opinion varies on this point.

### Serializers

A serializer translates data into a format that is easy to consume over the internet, typically JSON, and is displayed at an API endpoint. We will also cover serializers and JSON in more depth in following chapters. For now I want to demonstrate how easy it is to create a serializer with Django REST Framework to convert Django models to JSON.

Make a serializers.py file within our api app.
```
# api/serializers.py
from rest_framework import serializers

from books.models import Book


class BookSerializer(serializers.ModelSerializer):
    class Meta:
        model = Book
        fields = ('title', 'subtitle', 'author', 'isbn')
```
On the top lines we import Django REST Framework’s serializers class and the Book model from our books app. We extend Django REST Framework’s ModelSerializer into a BookSerializer class that specifies our database model Book and the database fields we wish to expose: title, subtitle, author, and isbn.

That’s it! We’re done.