## 1. What is DRF API?

**DRF (Django REST Framework)** is a powerful framework built on top of Django that is used to build **RESTful APIs**.

An **API (Application Programming Interface)** allows different applications to communicate with each other by exchanging data, usually in **JSON** format.

For example:

- Mobile App → DRF API → Django Server
- React Frontend → DRF API → Django Backend

Instead of returning HTML pages, DRF returns JSON responses.

### Features

- Serialization
- Authentication
- Permissions
- Pagination
- Filtering
- ViewSets
- Routers
- Browsable API

---

## 2. What is ViewSet in DRF?

A **ViewSet** is a class that combines multiple CRUD operations into a single class.

Instead of creating separate views for:

- Create
- List
- Retrieve
- Update
- Delete

We can use a **ModelViewSet**, which provides all CRUD operations automatically.

### Advantages

- Less code
- Easy URL routing using Routers
- Faster development
- Better code reusability

### Types of ViewSets

- ViewSet
- GenericViewSet
- ModelViewSet
- ReadOnlyModelViewSet

---

## 3. What is `@api_view` Decorator?

`@api_view` is a decorator provided by Django REST Framework for **Function-Based Views (FBVs)**.

It specifies which HTTP methods are allowed.

Example:

```python
@api_view(['GET'])
```

Only GET requests are accepted.

Example:

```python
@api_view(['GET', 'POST'])
```

Allows both GET and POST requests.

### Benefits

- Restricts allowed HTTP methods
- Enables DRF Request and Response objects
- Supports DRF features like authentication, permissions, and status codes

---

## 4. Difference Between Serializer and ModelSerializer

| Serializer | ModelSerializer |
|------------|-----------------|
| Fields are defined manually | Fields are generated automatically from the model |
| Must write `create()` and `update()` methods | Automatically provides `create()` and `update()` |
| More customization | Faster development |
| Used for custom or non-model data | Used with Django models |

### Serializer Example

```python
class StudentSerializer(serializers.Serializer):
    name = serializers.CharField()
    age = serializers.IntegerField()
```

### ModelSerializer Example

```python
class StudentSerializer(serializers.ModelSerializer):
    class Meta:
        model = Student
        fields = "__all__"
```

---

## 5. What are Check Constraints?

A **Check Constraint** is a database-level rule that ensures only valid data is stored.

### Examples

- Age must be greater than or equal to 18.
- Salary must be greater than 0.

Example:

```python
models.CheckConstraint(
    check=models.Q(age__gte=18),
    name="age_greater_than_18"
)
```

### Advantages

- Prevents invalid data
- Maintains data integrity
- Validation is enforced by the database

---

## 6. What are Forms in Django?

A **Django Form** is used to collect, validate, and process user input.

### Common Examples

- Login
- Signup
- Contact Form
- Profile Update
- Password Reset

### Benefits

- Input validation
- CSRF protection
- Easy rendering in templates
- Access to cleaned data

### Types of Forms

#### 1. Form

Fields are defined manually.

```python
class ContactForm(forms.Form):
    name = forms.CharField()
```

#### 2. ModelForm

Fields are generated automatically from a Django model.

```python
class PostForm(forms.ModelForm):
    class Meta:
        model = Post
        fields = "__all__"
```

---

## 7. What is Pagination?

Pagination divides a large dataset into smaller pages instead of loading everything at once.

### Example

Instead of loading 10,000 records, the application loads only 20 records per page.

### Benefits

- Faster page loading
- Better performance
- Lower memory usage
- Improved user experience

### Pagination in Django

```python
Paginator
```

### Pagination in DRF

- PageNumberPagination
- LimitOffsetPagination
- CursorPagination

---

## 8. What is Multi Match in Elasticsearch?

`multi_match` is an Elasticsearch query that searches the same keyword across multiple fields.

Instead of searching only one field, it searches multiple fields like:

- title
- description
- username
- bio

### Example

Searching for:

```
Python
```

Checks multiple fields such as:

- title
- description
- author

### Advantages

- Searches multiple fields simultaneously
- Produces more relevant search results
- Improves search experience

---

## 9. Difference Between `append()` and `extend()`

| append() | extend() |
|-----------|----------|
| Adds the entire object as one element | Adds each element individually |
| Creates a nested list when adding a list | Does not create a nested list |
| Length increases by 1 | Length increases by the number of added elements |
| Accepts any object | Accepts an iterable |

### append() Example

```python
numbers = [1, 2]
numbers.append([3, 4])

print(numbers)
```

**Output**

```python
[1, 2, [3, 4]]
```

### extend() Example

```python
numbers = [1, 2]
numbers.extend([3, 4])

print(numbers)
```

**Output**

```python
[1, 2, 3, 4]
```
