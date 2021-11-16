# [reading-note-401](https://mohammadsilwadi.github.io/reading-note-401/)
##  Django Best Practices: Custom User Model
### Setup
To start, create a new Django project from the command line. We need to do several things:

+ create and navigate into a dedicated directory called accounts for our code
+ install Django
+ make a new Django project called config
+ make a new app accounts
+ start the local web server

```
Here are the commands to run:

$ cd ~/Desktop
$ mkdir accounts && cd accounts
$ pipenv install django~=3.1.0
$ pipenv shell
(accounts) $ django-admin.py startproject config .
(accounts) $ python manage.py startapp accounts
(accounts) $ python manage.py runserver
```

### AbstractUser vs AbstractBaseUser
There are two modern ways to create a custom user model in Django: AbstractUser and AbstractBaseUser. In both cases we can subclass them to extend existing functionality however AbstractBaseUser requires much, much more work.

### Custom User Model
Creating our initial custom user model requires four steps:

+ update config/settings.py
+ create a new CustomUser model
+ create new UserCreation and UserChangeForm
+ update the admin
```
# config/settings.py
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'accounts', # new
]
...
AUTH_USER_MODEL = 'accounts.CustomUser' # new
```
```
# accounts/models.py
from django.contrib.auth.models import AbstractUser
from django.db import models

class CustomUser(AbstractUser):
    pass
    # add additional fields in here

    def __str__(self):
        return self.username
```
```
# accounts/forms.py
from django import forms
from django.contrib.auth.forms import UserCreationForm, UserChangeForm
from .models import CustomUser

class CustomUserCreationForm(UserCreationForm):

    class Meta:
        model = CustomUser
        fields = ('username', 'email')

class CustomUserChangeForm(UserChangeForm):

    class Meta:
        model = CustomUser
        fields = ('username', 'email')
```
```
# accounts/admin.py
from django.contrib import admin
from django.contrib.auth.admin import UserAdmin

from .forms import CustomUserCreationForm, CustomUserChangeForm
from .models import CustomUser

class CustomUserAdmin(UserAdmin):
    add_form = CustomUserCreationForm
    form = CustomUserChangeForm
    model = CustomUser
    list_display = ['email', 'username',]

admin.site.register(CustomUser, CustomUserAdmin)
```
```
(accounts) $ python manage.py makemigrations accounts
(accounts) $ python manage.py migrate
```
### Superuser
```
(accounts) $ python manage.py createsuperuser
```
### Templates/Views/URLs
```
# config/settings.py
TEMPLATES = [
    {
        ...
        'DIRS': [str(BASE_DIR.joinpath('templates'))], # new
        ...
    },
]
```
```
# config/settings.py
LOGIN_REDIRECT_URL = 'home'
LOGOUT_REDIRECT_URL = 'home'
```
### Then create four templates:
```
(accounts) $ touch templates/registration/login.html
(accounts) $ touch templates/registration/signup.html
(accounts) $ touch templates/base.html
(accounts) $ touch templates/home.html
```
### Update the files as follows:
```

Now for our urls.py files at the project and app level.

# config/urls.py
from django.contrib import admin
from django.urls import path, include
from django.views.generic.base import TemplateView

urlpatterns = [
    path('', TemplateView.as_view(template_name='home.html'), name='home'),
    path('admin/', admin.site.urls),
    path('accounts/', include('accounts.urls')),
    path('accounts/', include('django.contrib.auth.urls')),
]
Create a urls.py file in the accounts app.

(accounts) $ touch accounts/urls.py
Then fill in the following code:

# accounts/urls.py
from django.urls import path
from .views import SignUpView

urlpatterns = [
    path('signup/', SignUpView.as_view(), name='signup'),
]
Last step is our views.py file in the accounts app which will contain our signup form.

# accounts/views.py
from django.urls import reverse_lazy
from django.views.generic.edit import CreateView

from .forms import CustomUserCreationForm

class SignUpView(CreateView):
    form_class = CustomUserCreationForm
    success_url = reverse_lazy('login')
    template_name = 'registration/signup.html'
```
![](https://learndjango.com/static/images/tutorials/custom_user_model/login.png)
