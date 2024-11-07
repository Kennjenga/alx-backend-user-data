# README

## Resources

Read or watch:

- [What Is PII, non-PII, and Personal Data?](#)
- [logging documentation](#)
- [bcrypt package](#)
- [Logging to Files, Setting Levels, and Formatting](#)

## Learning Objectives

At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

- Examples of Personally Identifiable Information (PII)
- How to implement a log filter that will obfuscate PII fields
- How to encrypt a password and check the validity of an input password
- How to authenticate to a database using environment variables

## Summary

### Personally Identifiable Information (PII)

PII refers to any data that can be used to identify a specific individual. Examples include:

- Full name
- Social Security Number
- Email address
- Phone number

### Log Filter to Obfuscate PII Fields

To protect sensitive information in logs, you can implement a log filter that obfuscates PII fields. For example, using Python's logging module, you can create a custom filter:

```python
import logging

class PIIObfuscator(logging.Filter):
    def filter(self, record):
        record.msg = record.msg.replace("email@example.com", "[REDACTED]")
        return True

logger = logging.getLogger()
logger.addFilter(PIIObfuscator())
```

### Encrypting Passwords with bcrypt

To securely store passwords, you can use the `bcrypt` package to hash and verify passwords:

```python
import bcrypt

# Hash a password
password = b"super_secret_password"
hashed = bcrypt.hashpw(password, bcrypt.gensalt())

# Check the validity of an input password
if bcrypt.checkpw(password, hashed):
    print("Password is valid")
else:
    print("Invalid password")
```

### Authenticating to a Database Using Environment Variables

To securely authenticate to a database, store credentials in environment variables:

```python
import os
import psycopg2

# Retrieve credentials from environment variables
db_user = os.getenv('DB_USER')
db_password = os.getenv('DB_PASSWORD')

# Connect to the database
conn = psycopg2.connect(
    dbname="example_db",
    user=db_user,
    password=db_password,
    host="localhost"
)
```

By following these practices, you can ensure that sensitive information is protected and your application remains secure.
