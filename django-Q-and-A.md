# 1. How do we create a virtual environment in Python?

To create a virtual environment in Python, use the built-in `venv` module.

## Command:
```bash
python3 -m venv venv
```

* 'venv' creates an isolated environment for Python projects.
* It helps manage dependencies separately for each project.

----

# 2. How do we deactivate a virtual environment?

## Command:
```bash
deactivate
```

* 'deactivate' is a command that exits the current virtual environment and returns to the global Python environment.

----

# 3. How do we create a distribution build for a Django project?

## Command:
```bash
python3 setup.py sdist bdist_wheel
```

* Creates source (sdist) and wheel (bdist_wheel) distributions.
* Used for packaging and sharing Python/Django projects.

----

# 4. What is the use of admin.site.urls in Django?

In Django, 
* admin.site.urls is used to include Django's built-in admin interface URLs.
* It allows access to the admin panel.

## Example:

```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    # other URLs...
]
```

-----

# 5. What is the default database in Django?

* The default database in Django is SQLite.
* It is a lightweight, file-based database that does not require a separate server.

-----

# 6. Why do we create reusable apps in Django?

* Reusable apps allow us to share code across multiple projects.
* They promote code reuse and maintainability.

-----

# 7. Command to run tests in Django

## Command:
```bash
python manage.py test
```

* Runs all test cases defined in the project.
* Uses Django's built-in testing framework.

-----

# 8. Difference between Authentication and Authorization.

### Authentication
* `Authentication` verifies the identity of a user.
* Example: When a user logs in, their credentials are authenticated to verify their identity.

### Authorization
* `Authorization` determines what a user can do after they are authenticated.
* Example: After authentication, a user may be authorized to access certain resources or perform certain actions.

-----

# 9. How do we use a Django admin page?

* The Django admin page is a built-in interface for managing database records.
* It allows administrators to create, update, and delete records without writing custom views.

-----

# 10. What is the use of include() method?

* `include()` is used to include URLs from other apps or modules.
* It allows us to organize URLs in a modular way, separating them into different files or apps.

## Example:
```python
from django.urls import include, path

urlpatterns = [
    path('admin/', admin.site.urls),
    path('blog/', include('blog.urls')),
]
```

-----

# 11. What does CASCADE do in Django? 

* `CASCADE` is a deletion rule that deletes related objects when the parent object is deleted.
* Example: If a `Post` is deleted, all `Comment` objects related to it will also be deleted.

## Example:
```python
models.ForeignKey(Author, on_delete=models.CASCADE)
```

-----

# 12. Command to fetch all records from DB in Django

## Explanation:
* `python manage.py shell` is used to open the Django shell, which allows you to interact with the database.
* `Model.objects.all()` is used to fetch all records from the database.

## Example:
```python
python manage.py shell
>>> from blog.models import Post
>>> Post.objects.all()
```

-----

# 13. Why do we use namespacing in Django?

* Namespacing allows us to avoid naming conflicts between different apps or modules.
* It helps to organize URLs and models in a modular way, making the codebase easier to maintain.

## Example:

```python
from django.urls import include, path

urlpatterns = [
    path('admin/', admin.site.urls),
    path('blog/', include('blog.urls', namespace='blog')),
]
```

----

# 14. What is migrations in Django?

* Migrations are used to manage changes to the database schema over time.
* They allow you to define database schema changes in code and apply them to the database.

## Example:
```python
python manage.py makemigrations
python manage.py migrate
```
