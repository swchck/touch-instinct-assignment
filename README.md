# Example API

This is an example API that uses Swagger to document its endpoints.

## PIN code and biometric auth

> All operations with PIN code and biometric auth should be performed on application side

- *PIN code should be created on first login*
- *If biometric auth wasn't succesfull request PIN code input*
- *If user prvided wrong PIN 3 times, call `/logout`*

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

### /forgot/password

- *If user forgot password he should be able to recover it via request with login and description in comment field*

- `POST`: Request password recovery

### /forgot/login

- *If user forgot login too, he should be able to provide additional information, like bith date via request with description in comment field*

- `POST`: Request login recovery

### /welcome

- *Endpoint should return welcome message, it would be used for promo, jokes, etc., without changes on application side*

- `GET`: Get welcome message

### /card

- `GET`: Get list of cards

### /card/{card_id}

- `GET`: Get card by ID
- `POST`: Block card

### /card/{card_id}/transaction

- `GET`: Get list of transactions

### /card/{card_id}/transaction/{transaction_id}

- `GET`: Get transaction by ID
- `POST`: Create transaction dispute

### /complain

- `GET`: Get list of complains
- `POST`: Create complain

## Authentication

The API uses JWT authentication. To authenticate, send a `POST` request to `/login` with a username and password in the request body. This will return an access token that can be used to access protected endpoints.

To access protected endpoints, include the access token in the `Authorization` header of your requests.
