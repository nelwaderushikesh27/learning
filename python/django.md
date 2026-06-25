# Django Notes

## 📌 Key Concepts

### What is Django?
A high-level Python web framework for rapid development.

## 🚀 Creating a Project

```bash
django-admin startproject myproject
cd myproject
python manage.py runserver
```

## 📂 Project Structure

```
myproject/
├── manage.py
├── myproject/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
└── myapp/
    ├── models.py
    ├── views.py
    ├── urls.py
    └── templates/
```

## 📦 Creating Models

```python
from django.db import models

class Todo(models.Model):
    title = models.CharField(max_length=200)
    description = models.TextField()
    completed = models.BooleanField(default=False)
    created_at = models.DateTimeField(auto_now_add=True)
    
    def __str__(self):
        return self.title
```

## 🛣️ URLs & Views

```python
# urls.py
from django.urls import path
from . import views

urlpatterns = [
    path('', views.home, name='home'),
    path('todos/', views.todo_list, name='todo-list'),
]

# views.py
from django.shortcuts import render
from .models import Todo

def todo_list(request):
    todos = Todo.objects.all()
    return render(request, 'todos.html', {'todos': todos})
```

## 📚 Resources

- [Django Docs](https://docs.djangoproject.com/)
- [Django Girls Tutorial](https://tutorial.djangogirls.org/)

---
*Notes by Rushikesh*
