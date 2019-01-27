# Getting Started With Kubernetes

![](pictures/kubernetes_logo.png)

- ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) `Kubernetes is an open source container orchestration engine for automating deployment, scaling, and management of containerized applications.`
- ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) `It groups containers that make up an application into logical units for easy management and discovery.`
- ![#1589F0](https://placehold.it/15/1589F0/000000?text=+) `Kubernetes is a container orchestration system for Docker containers that is more extensive than Docker Swarm and is meant to coordinate clusters of nodes at scale in production in an efficient manner.`

## REQUIREMENTS:

```
- You should have good knowledge of docker to get hands on [kubernetes](https://kubernetes.io/):
- It is good to have [Linux](https://www.linux.org/) OS.
- Have [Docker](http://docs.docker.com/engine/installation/) Installed.
- Have an account on [Docker Hub](https://hub.docker.com)
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