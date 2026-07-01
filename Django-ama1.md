# Django AMA Questions and Answers

## 1. What is the purpose of Django apps?

A Django app is a reusable module that implements a specific
feature of a project. Instead of putting all code into one place, Django
encourages splitting functionality into separate apps.

**Examples:** - `users` -- authentication and profiles - `posts` --
create and manage posts - `feed` -- home feed - `comments` -- comment
system

**Benefits:** - Modular and reusable - Easier maintenance - Better team
collaboration - Cleaner project structure

------------------------------------------------------------------------

## 2. What is Elasticsearch?

Elasticsearch is a distributed search and analytics engine
used to perform very fast searches on large datasets.

**Why use it?** - Full-text search - Auto-complete - Typo tolerance
(fuzzy search) - Filtering and ranking - Scales to millions of records

**Example:** Searching Instagram users or hashtags instantly.

------------------------------------------------------------------------

## 3. How does Django hash passwords?

Django never stores plain-text passwords. It hashes
passwords using secure algorithms before saving them.

``` python
from django.contrib.auth.models import User

user = User.objects.create_user(
    username="john",
    password="mypassword123"
)
```

During login, Django hashes the entered password and compares it with
the stored hash.

**Benefits:** - Better security - Passwords cannot be easily recovered -
Protects user accounts

------------------------------------------------------------------------

## 4. How does pagination work?

Pagination divides large datasets into smaller pages.

Example: - 100 posts - 10 posts per page - Total pages = 10

Django example:

``` python
from django.core.paginator import Paginator

paginator = Paginator(posts, 10)
page = request.GET.get("page")
posts = paginator.get_page(page)
```

**Benefits:** - Faster page loading - Reduced server load - Better user
experience

------------------------------------------------------------------------

## 5. What is Celery?

Celery is a task queue used to execute background and
asynchronous tasks.

**Common uses:** - Sending emails - Notifications - Image processing -
Scheduled jobs - Report generation

Celery commonly works with Redis or RabbitMQ as a message broker.

------------------------------------------------------------------------

## 6. What is `SECRET_KEY` in Django?

`SECRET_KEY` is a secret value used for cryptographic
operations.

It helps: - Sign sessions - Protect CSRF tokens - Sign cookies -
Generate password reset tokens

It should never be committed to GitHub and is usually stored in
environment variables.

------------------------------------------------------------------------

## 7. What is Docker?

Docker is a containerization platform that packages an
application with all its dependencies.

**Advantages:** - Same environment everywhere - Easy deployment -
Isolation - Portability

Example: A Django app runs the same on your laptop, testing server, and
production server.

------------------------------------------------------------------------

## 8. What is fuzziness?

Fuzziness is an Elasticsearch feature that finds similar
words even if the user makes spelling mistakes.

Examples: - `instgram` → `instagram` - `djnago` → `django`

Useful for improving search results.

------------------------------------------------------------------------

## 9. What is `request.POST`? What are decorators?

### `request.POST`

`request.POST` is a dictionary-like object containing form data sent
using the HTTP POST method.

Example:

``` python
username = request.POST.get("username")
```

### Decorators

Decorators modify the behavior of a function without changing its code.

Example:

``` python
from django.contrib.auth.decorators import login_required

@login_required
def profile(request):
    ...
```

Common decorators: - `@login_required` - `@require_POST` -
`@csrf_exempt`

------------------------------------------------------------------------

## 10. What is `dj-database-url`?

`dj-database-url` converts a database URL into Django's
`DATABASES` configuration.

Example:

``` python
import dj_database_url

DATABASES = {
    "default": dj_database_url.parse(
        "postgres://user:password@host:5432/dbname"
    )
}
```

It is commonly used on Render, Heroku, and Railway.

------------------------------------------------------------------------

## 11. Difference between AnonymousUser and User

  AnonymousUser                   User
  ------------------------------- --------------------------------------
  Not logged in                   Logged in
  `is_authenticated = False`      `is_authenticated = True`
  No database record              Exists in the database
  Cannot access protected pages   Can access authorized pages
  Limited permissions             Permissions depend on assigned roles

**Example:**

``` python
if request.user.is_authenticated:
    print("Logged in")
else:
    print("Guest user")
```