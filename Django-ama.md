# Django Interview Questions & Answers

## 1. What is the DRY Principle in Django?


**DRY** stands for **Don't Repeat Yourself**.

It means we should avoid writing the same code multiple times. Instead, write it once and reuse it.

### Examples

* Using `base.html` with template inheritance.
* Creating reusable functions.
* Using model inheritance.
* Creating reusable forms.
* Creating custom template tags.

### Example

```html
{% extends "base.html" %}
```

---

# 2. What is the difference between Middleware and Signals?

## Middleware

* Works during the request-response cycle.
* Processes every HTTP request and response.
* Configured in `settings.py`.

## Signals

* Trigger when model events occur.
* Used for events like `post_save`, `pre_save`, and `post_delete`.
* Usually written in `signals.py`.

### Example

**Middleware**

* Authentication
* Logging
* Security

**Signals**

* Automatically create a Profile when a User is created.
* Send an email after an order is placed.


---

# 3. What is the difference between CreateView and TemplateView?

## CreateView

* Used to create database records.
* Uses forms.
* Saves data into the database.

Example:

```python
class PostCreateView(CreateView):
    model = Post
    form_class = PostForm
```

## TemplateView

* Used only to render templates.
* Does not save data.
* Mostly used for static pages.

Example:

```python
class AboutView(TemplateView):
    template_name = "about.html"
```

---

# 4. What is the use of the WSGI file?


WSGI stands for **Web Server Gateway Interface**.

The `wsgi.py` file connects Django with the web server (such as Gunicorn or uWSGI). It allows the web server to communicate with your Django application.

---

# 5. Can you edit old migrations?

Yes, but only if they have **not been applied** or **are not shared with others**.

If migrations are already applied in production, do **not** edit them.

Instead:

```bash
python manage.py makemigrations
python manage.py migrate
```

---

# 6. Why should we update `AUTH_USER_MODEL` in `settings.py`?

When using a custom User model, Django must know which model represents users.

Example:

```python
AUTH_USER_MODEL = "users.User"
```

Without this setting:

* Django uses the default User model.
* Your custom User model will not work correctly.
* ForeignKey relationships may break.

---

# 7. Does `SET_NULL` work without `null=True`?

**No.**

Example:

```python
author = models.ForeignKey(
    User,
    on_delete=models.SET_NULL,
    null=True
)
```

Without `null=True`, Django raises an error because it cannot store `NULL`.

---

# 8. What is `blank=True` in Django models?

`blank=True` allows a field to be left empty during form validation and in the Django admin.

Example:

```python
bio = models.TextField(blank=True)
```

---

# 9. What is the difference between a Library and a Package?

## Library

A library is a collection of reusable code that provides functionality.

Examples:

* NumPy
* Pandas
* Requests

## Package

A package is a directory containing Python modules and an `__init__.py` file.

Example:

```text
myapp/
    __init__.py
    views.py
    models.py
```

---

# 10. What is `enctype="multipart/form-data"`?


It is required when uploading files through an HTML form.

Example:

```html
<form method="POST" enctype="multipart/form-data">
```

Without it:

* Images
* PDFs
* Videos

cannot be uploaded properly.

In Django, uploaded files are accessed using:

```python
request.FILES
```

---

# 11. What is Lazy Loading?

Lazy loading means data is loaded **only when it is needed**.

Django QuerySets are lazy.

Example:

```python
users = User.objects.all()
```

No SQL query is executed yet.

The query runs only when the data is accessed:

```python
for user in users:
    print(user.username)
```

or

```python
list(users)
```

### Advantages

* Improves performance.
* Reduces unnecessary database queries.
* Saves memory.

