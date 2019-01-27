# Getting Started With Kubernetes

![](pictures/kubernetes_logo.png)

- ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) `Django is a high-level Python Web framework that encourages rapid development and clean, pragmatic design`
- ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) `Built by experienced developers, it takes care of much of the hassle of Web development.`
- ![#1589F0](https://placehold.it/15/1589F0/000000?text=+) `So you can focus on writing your app without needing to reinvent the wheel. It’s free and open source.`

## REQUIREMENTS:

These are the important libraries that you will need in order to process this project:

```
- Django
- Scipy
- SQlite3
- Numpy
- Matplotlib
```
    
### NOTE:

You can download Django from this site [https://www.djangoproject.com/download/](https://www.cryptonator.com/api).

## LINKS:

This project was built using this link [Django Documentation](https://www.djangoproject.com/).

## Commands:
 
 ``` 
# Start Project:
- django-admin startproject project_name 

 # Run Server:
 - python3 manage.py runserver

 # Importings
 - from django.shortcuts import render
 - from django.http import HttpResponse
 - from django.urls import path,include
 - from django.conf.urls import url,include

# Apps Creating: 
 -python3 manage.py app_name 
 - Register it on settings.py file under apps 
 
 # Migration Commands:
 - python3 manage.py makemigrations (first perform this)
 - python3 manage.py migrate

 # SuperUser:
 - python3 manage.py createsuperuser

 ```

### Django ORM (Interactive Shell):
```
 (ORM bridges the gap between the code and Database, so that we can 
 interact with database to retrieve ,save and perform various operation from with database.)

 - python3 manage.py shell
```
 ![](screenshots/models.png)

### Admin section (http://127.0.0.1:8000/admin/):
```
 You can access admin section like this.
```
 ![](screenshots/admin.png)

### Html Tags:
```
 {% 'Python code goes here' %}
 {{ 'Data goes here' }}
```
 ![](screenshots/html_tags.png)

### Static Files:
```
 {% load static from staticfiles %}
 # Can also work with (STATIC_URL = '/static/files/') because we import static from staticfiles
 # static = STATIC_URL
 
 from django.contrib.staticfiles.urls import staticfiles_urlpatterns 

 urlpatterns += staticfiles_urlpatterns()

```
 ![](screenshots/stars_ss.png)

### Url Parameters:
```
 url(r'^(?P<keyword>[\w-]+)/$')
```
 ![](screenshots/url_params.png)

### Media Files:
```
MEDIA_URL = '/media/'

MEDIA_ROOT = (
    os.path.join(BASE_DIR,'media')
)

 from django.conf.urls.static import static
 from django.conf import settings

 urlpatterns += static(settings.MEDIA_URL,document_root=settings.MEDIA_ROOT)
```
### Saving Users:
```
 {% csrf_token %} should be in data which is sending for GET request
 html form (action)-->  <form class="site-form" action="/accounts/signup" method="post">
 redirect('<'app_name'>:<'url_name'>) --> redirect('articles:list')
```
![](screenshots/token.png)