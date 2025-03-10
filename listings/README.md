# alx_travel_app_0x00

## Getting Started with Django REST Framework

This page provides an overview of Django REST Framework (DRF), its key architecture components, and the steps to set up a basic Django project with DRF.

## Concept Overview

Django REST Framework (DRF) is a powerful and flexible toolkit for building Web APIs. It extends Django’s capabilities to facilitate the development of RESTful APIs, providing features like serialization, authentication, permissions, and more. This concept introduces you to the fundamental aspects of DRF and guides you through setting up a basic API endpoint.

## Topics

DRF Architecture: Serializers, ViewSets, Routers
Creating Your First API Endpoint

### Objectives

* Understand the purpose and features of the Django REST Framework
* Familiarize with the key components of DRF architecture
* Learn how to create a basic API endpoint using DRF.

## Introduction to Django REST Framework

DRF provides a structured and efficient way to build APIs with Django. It simplifies common tasks like data serialization, validation, authentication, and permission handling. This allows you to focus on the logic of your API without worrying about the underlying details.

## Benefits of DRF:

### Serialization: 
DRF simplifies the process of converting complex data structures, such as Django models, into formats like JSON or XML, making it suitable for consumption by various clients.

### ViewSets and Routers: 
DRF offers viewsets and routers that streamline the process of creating API endpoints, reducing boilerplate code and promoting consistency.

### Authentication and Permissions: 
DRF provides built-in support for various authentication methods and permission policies, ensuring secure access to your API.

### Browsable API: 
DRF includes a browsable API interface that allows developers to easily interact with and test API endpoints directly from a web browser.

## Creating Your First API Endpoint

To get started with Django REST Framework, follow these steps:

* Create a new Django project and app:
django-admin startproject my_project
cd my_project
python manage.py startapp my_app

* Install the Django REST Framework package:
pip install djangorestframework
Add 'rest_framework' to your INSTALLED_APPS in the settings.py file.

INSTALLED_APPS = [
    ...
    'rest_framework',
]

* Define your first model in the models.py file of your app:

from django.db import models

cls


* Create a serializer for your model in the serializers.py file:

from rest_framework import serializers
from .models import Book

class BookSerializer(serializers.ModelSerializer):
    class Meta:
        model = Book
        fields = '__all__'

* Define a view for your model in the views.py file:

from rest_framework import generics
from .models import MyModel
from .serializers import MyModelSerializer

class BookListCreateAPIView(generics.ListCreateAPIView):
    queryset = Book.objects.all()
    serializer_class = BookSerializer

* Add a URL pattern for your view in the urls.py file:

pythonCopy codefrom django.urls import path
from .views import BookListCreateAPIView

urlpatterns = [
    path("api/books", views.BookListCreateAPIView.as_view(), name="book_list_create"),
]

* Start the development server and access your API endpoint at http://localhost:8000/my-models/. Now you have a basic API endpoint that allows you to perform CRUD operations on your model.

python manage.py runserver

## Practice Exercise

Extend the BookSerializer to include a custom field that displays the number of days since the model instance was created.

Install Django REST Framework and set up a basic API endpoint for a model in your existing Django project.

Use the browsable API interface to explore the available actions and test your API endpoints.
Experiment with different serializer fields and viewset actions.