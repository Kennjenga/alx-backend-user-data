This module demonstrates a basic authentication system using Flask for educational purposes.
In a real-world application, it is recommended to use established modules or frameworks for authentication, such as Flask-User.

Resources:

- Flask documentation: https://flask.palletsprojects.com/
- Requests module: https://docs.python-requests.org/
- HTTP status codes: https://developer.mozilla.org/en-US/docs/Web/HTTP/Status

Learning Objectives:
By the end of this project, you should be able to:

1. **Declare API routes in a Flask app**:

   - Example:
     ```python
     @app.route('/login', methods=['POST'])
     def login():
           return "Login Page"
     ```
   - Description: This demonstrates how to create a new route in a Flask application that listens for POST requests at the `/login` endpoint.

2. **Get and set cookies**:

   - Example:
     ```python
     @app.route('/set_cookie')
     def set_cookie():
           resp = make_response("Setting a cookie")
           resp.set_cookie('username', 'admin')
           return resp
     ```
   - Description: This shows how to set a cookie named `username` with the value `admin` in the user's browser.

3. **Retrieve request form data**:

   - Example:
     ```python
     @app.route('/submit', methods=['POST'])
     def submit():
           username = request.form['username']
           return f"Received username: {username}"
     ```
   - Description: This demonstrates how to retrieve data from a form submission, specifically the `username` field from the request.

4. **Return various HTTP status codes**:
   - Example:
     ```python
     @app.route('/not_found')
     def not_found():
           return "Page not found", 404
     ```
   - Description: This shows how to return a custom message along with a specific HTTP status code, in this case, a 404 Not Found error.

Note: This implementation is for learning purposes only and should not be used in production environments.
