# Interview Questions and Answers

## 1. What is an Anagram?

**Answer:**

An **anagram** is a word or phrase formed by rearranging the letters of
another word or phrase while using all the original letters exactly
once.

**Examples** - listen → silent - evil → vile - heart → earth

**Python Example**

``` python
def is_anagram(s1, s2):
    return sorted(s1.lower()) == sorted(s2.lower())

print(is_anagram("listen", "silent"))  # True
print(is_anagram("hello", "world"))    # False
```

**Time Complexity:** O(n log n)

------------------------------------------------------------------------

## 2. What is the Default Port of Django?

The default development server port in Django is **8000**.

Start the server:

``` bash
python manage.py runserver
```

Open:

    http://127.0.0.1:8000/

Change the port:

``` bash
python manage.py runserver 8080
```

------------------------------------------------------------------------

## 3. What is Docker Compose?

Docker Compose is a tool used to define and manage **multiple Docker
containers** using a single YAML file (`docker-compose.yml` or
`compose.yaml`).

Example:

``` yaml
services:
  web:
    build: .
    ports:
      - "8000:8000"

  db:
    image: postgres
```

Commands:

``` bash
docker compose up
docker compose down
```

**Advantages** - Manages multiple containers - Creates networking
automatically - Supports volumes and environment variables - Starts the
entire application with one command

------------------------------------------------------------------------

## 4. Types of Exchanges in RabbitMQ

### 1. Direct Exchange

Routes messages using an **exact routing key**.

### 2. Fanout Exchange

Broadcasts messages to **all bound queues**. Routing key is ignored.

### 3. Topic Exchange

Routes messages using wildcard patterns.

-   `*` = one word
-   `#` = zero or more words

### 4. Headers Exchange

Routes messages based on **message headers** instead of routing keys.

  Exchange   Uses Routing Key   Use Case
  ---------- ------------------ ----------------------
  Direct     Yes                Exact routing
  Fanout     No                 Broadcast
  Topic      Yes                Pattern matching
  Headers    No                 Header-based routing

------------------------------------------------------------------------

## 5. How to List All Containers in Docker?

Running containers:

``` bash
docker ps
```

All containers:

``` bash
docker ps -a
```

Only container IDs:

``` bash
docker ps -q
```

------------------------------------------------------------------------

## 6. What is a Durable Queue in RabbitMQ?

A **durable queue** survives a RabbitMQ server restart.

Example:

``` python
channel.queue_declare(
    queue="emails",
    durable=True
)
```

> Note: Messages should also be published as **persistent** to survive
> server restarts.

------------------------------------------------------------------------

## 7. Types of Networks in Docker

### Bridge

Default network for containers on a single host.

### Host

Container shares the host's network.

### None

No network access.

### Overlay

Used for communication across multiple Docker hosts (Docker Swarm).

### Macvlan

Assigns a MAC address so the container appears as a physical device.

  Network   Use Case
  --------- ---------------------------
  Bridge    Single-host communication
  Host      Share host network
  None      No networking
  Overlay   Multi-host communication
  Macvlan   Physical network access

------------------------------------------------------------------------

## 8. What is the Use of Docker Volumes?

Docker volumes provide **persistent storage**.

Without a volume: - Delete container → Data is lost.

With a volume: - Delete container → Data remains.

Create a volume:

``` bash
docker volume create myvolume
```

Use a volume:

``` bash
docker run -v myvolume:/data nginx
```

List volumes:

``` bash
docker volume ls
```

**Advantages** - Persistent storage - Share data between containers -
Easier backups - Recommended for databases

---------------------------------------------------------------------------------

## 9. What is Redis and why it is fast?

Redis is an in-memory data store used for caching and real-time applications. It is fast because it stores data in RAM, avoids disk access, and performs most operations in O(1) time complexity.