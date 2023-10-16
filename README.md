# Example API

This is an example API that uses Swagger to document its endpoints.

## Endpoints

The API has the following endpoints:

### /login

- *Base validation of username and password should be performed on application side*
- *Auth button should be unactive till user didn't provide values to both fields*
- *If error recieved from backend application should provide button for password recovery*

- `PUT`: Perform authorization

### /logout

- *Logout should be performed if user could validate identity via passcode or couldn't pass biometric identification*

- `POST`: Revocate authorization

### /forgot-password

- *If user forgot password he should be able to recover it via request with login and description in comment field*

- `POST`: Request password recovery

### /forgot-login

- *If user forgot login too, he should be able to provide additional information, like bith date via request with description in comment field*

## Authentication

The API uses JWT authentication. To authenticate, send a `POST` request to `/login` with a username and password in the request body. This will return an access token that can be used to access protected endpoints.

To access protected endpoints, include the access token in the `Authorization` header of your requests.
