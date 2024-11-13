## Summary

This project involves implementing a Session Authentication system from scratch without using any external modules. The goal is to understand the mechanics of session authentication by building it step-by-step.

### install requirements

install from requirements.txt -- pip3 install -r requirements.txt
create basicauth user -- API_HOST=0.0.0.0 API_PORT=5000 AUTH_TYPE=basic_auth ./main_0.py
run server -- API_HOST=0.0.0.0 API_PORT=5000 AUTH_TYPE=basic_auth python3 -m api.v1.app
make request -- curl "http://0.0.0.0:5000/api/v1/users" -H "Authorization: Basic Ym9iQGhidG4uaW86SDBsYmVydG9uU2Nob29sOTgh"

## Resources

- [REST API Authentication Mechanisms (focus on session auth)](https://example.com/rest-api-authentication-mechanisms)
- [HTTP Cookie](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)
- [Flask](https://flask.palletsprojects.com/)
- [Flask Cookie](https://flask.palletsprojects.com/en/2.0.x/quickstart/#cookies)

## Objectives

By the end of this project, you should be able to:

- Explain what authentication means.
- Describe what session authentication entails.
- Understand what Cookies are and their role in session management.
- Know how to send and parse Cookies in HTTP requests and responses.

## Description

This project aims to provide a comprehensive understanding of session authentication by implementing it from scratch. The objectives are designed to ensure that you gain a deep understanding of the following concepts:

1. **Authentication**: The process of verifying the identity of a user or system. This is a critical aspect of security in any application.
2. **Session Authentication**: A method of maintaining a user's authenticated state across multiple requests. This typically involves the use of session IDs stored in cookies.
3. **Cookies**: Small pieces of data sent from a server and stored on the client's device. Cookies are used to manage session state and track user activity.
4. **HTTP Requests and Responses**: Understanding how to send and parse cookies within HTTP requests and responses is crucial for implementing session management.
