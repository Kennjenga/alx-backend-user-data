# Basic Authentication

run server -- API_HOST=0.0.0.0 API_PORT=5000 AUTH_TYPE=basic_auth python3 -m api.v1.app
test endpoint: curl "http://0.0.0.0:5000/api/v1/users"

## Background Context

In this project, you will learn what the authentication process means and implement Basic Authentication on a simple API.

In the industry, you should not implement your own Basic authentication system and use a module or framework that does it for you (like in Python-Flask: Flask-HTTPAuth). Here, for learning purposes, we will walk through each step of this mechanism to understand it by doing.

## Resources

Read or watch:

- [REST API Authentication Mechanisms](https://www.youtube.com/watch?v=501dpx2IjGY)
- [Base64 in Python](https://docs.python.org/3.7/library/base64.html)
- [HTTP header Authorization](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Authorization)
- [Flask](https://palletsprojects.com/projects/flask/)
- [Base64 - concept](https://en.wikipedia.org/wiki/Base64)

## Learning Objectives

At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

### General

- What authentication means
- What Base64 is
- How to encode a string in Base64
- What Basic authentication means
- How to send the Authorization header

## Summary

### Authentication

Authentication is the process of verifying the identity of a user or system. It ensures that the entity requesting access is who they claim to be. This is a crucial aspect of security in any application.

### Base64

Base64 is an encoding scheme used to represent binary data in an ASCII string format. It is commonly used in various applications, including email via MIME and storing complex data in XML or JSON.

#### Example:

To encode a string in Base64 in Python:

```python
import base64

message = "Hello, World!"
encoded_message = base64.b64encode(message.encode())
print(encoded_message)
```

### Basic Authentication

Basic Authentication is a simple authentication scheme built into the HTTP protocol. The client sends HTTP requests with the `Authorization` header that contains the word `Basic` followed by a space and a base64-encoded string `username:password`.

#### Example:

To send the Authorization header in Python using the `requests` library:

```python
import requests
from requests.auth import HTTPBasicAuth

response = requests.get('https://api.example.com', auth=HTTPBasicAuth('username', 'password'))
print(response.status_code)
```
