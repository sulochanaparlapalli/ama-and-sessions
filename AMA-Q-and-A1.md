## 1. What is Celery?

Celery is a distributed task queue for Python used to execute
long-running or background tasks asynchronously. It works with a message
broker (such as Redis or RabbitMQ) to send tasks from an application to
worker processes.

**Use cases:** - Sending emails - Processing images/videos - Generating
reports - Scheduled tasks (using Celery Beat)

------------------------------------------------------------------------

## 2. What brokers does Celery support?

Celery supports multiple message brokers: - **RabbitMQ** (most
recommended for production) - **Redis** - Amazon SQS - Apache Kafka
(through community support) - Azure Service Bus - Google Cloud Pub/Sub
(via extensions)

RabbitMQ and Redis are the most commonly used brokers.

------------------------------------------------------------------------

## 3. What is currying in JavaScript?

Currying is the process of converting a function that takes multiple
arguments into a sequence of functions, each taking one argument.

``` javascript
function add(a){
    return function(b){
        return a + b;
    }
}
console.log(add(5)(3)); // 8
```

**Benefits** - Function reuse - Partial application - Cleaner code

------------------------------------------------------------------------

## 4. What is the use of the `x-match` attribute in a RabbitMQ Headers Exchange?

`x-match` determines how header matching is performed.

Values: - **all** → All headers must match. - **any** → At least one
header should match.

Example:

    x-match = all
    department = IT
    location = Bangalore

A message is routed only if both headers match.

------------------------------------------------------------------------

## 5. Difference between `slice()` and `splice()` in JavaScript

  slice()                    splice()
  -------------------------- -------------------------------------
  Returns a new array        Modifies the original array
  Does not change original   Changes original array
  Used to copy/extract       Used to add/remove/replace elements

Example:

``` javascript
let arr=[1,2,3,4];
console.log(arr.slice(1,3)); // [2,3]

arr.splice(1,2);
console.log(arr); // [1,4]
```

------------------------------------------------------------------------

## 6. What is the Call Stack in JavaScript?

The Call Stack is a LIFO (Last In, First Out) data structure that keeps
track of function execution.

Example:

``` javascript
function a(){ b(); }
function b(){ c(); }
function c(){ console.log("Hello"); }
a();
```

Execution order:

    a()
    ↓
    b()
    ↓
    c()
    ↓
    console.log()

After completion, functions are removed from the stack.

------------------------------------------------------------------------

## 7. What is Docker Compose?

Docker Compose is a tool used to define and manage multi-container
Docker applications using a `docker-compose.yml` file.

Example:

``` yaml
services:
  web:
    build: .
  redis:
    image: redis
```

Benefits: - Run multiple containers with one command. - Easy
networking. - Volume management.

Command:

``` bash
docker compose up
```

------------------------------------------------------------------------

## 8. Components of RabbitMQ

Main components: 1. Producer 2. Exchange 3. Queue 4. Binding 5. Routing
Key 6. Consumer 7. Channel 8. Connection 9. Virtual Host (vHost) 10.
Message Broker

------------------------------------------------------------------------

## 9. What is Memoization?

Memoization is an optimization technique where the result of expensive
function calls is cached so repeated inputs return the cached result.

Example:

``` javascript
const cache = {};
function square(n){
    if(cache[n]) return cache[n];
    cache[n] = n*n;
    return cache[n];
}
```

Benefits: - Improves performance - Reduces repeated computations

------------------------------------------------------------------------

## 10. Difference between Collection and Table in MongoDB

  Collection            Table
  --------------------- ------------------
  MongoDB               SQL Database
  Stores documents      Stores rows
  Schema is flexible    Schema is fixed
  JSON/BSON documents   Rows and columns

------------------------------------------------------------------------

## 11. What is Django Architecture?

Django follows the **MVT (Model-View-Template)** architecture.

-   **Model** → Database layer
-   **View** → Business logic
-   **Template** → User interface

Flow:

    User
     ↓
    URL
     ↓
    View
     ↓
    Model
     ↓
    Database
     ↓
    Template
     ↓
    Response

------------------------------------------------------------------------

## 12. What is Synchronous Execution?

Synchronous execution means tasks execute one after another. The next
task starts only after the previous one completes.

Example:

``` javascript
console.log("Start");
console.log("Middle");
console.log("End");
```

Output:

    Start
    Middle
    End

**Characteristics** - Sequential execution - Blocking - Easier to
understand but slower for long-running operations