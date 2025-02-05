# User Creation Endpoint

## Endpoint

**POST /register**

## Description

This endpoint creates a new user. It validates the incoming request data and returns a token along with the created user details upon success.

## Request Payload

- **fullname.firstname**: string (minimum 3 characters, required)
- **fullname.lastname**: string (required)
- **email**: string (valid email, required)
- **password**: string (minimum 6 characters, required)

## Validation

- The first name must be at least 3 characters long.
- The email must be a valid email address.
- The password must be at least 6 characters long.

## Response

- **Success (201)**: Returns a JSON object containing:
  - `token`: Authentication token.
  - `user`: The created user object.
- **Error (400)**: Returns a JSON object with an array of validation errors.

## Additional Notes

- The password is encrypted before being saved.
- The JWT token is generated using the user's `_id` and a secret from the environment.
