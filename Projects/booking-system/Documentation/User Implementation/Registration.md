
**1. Admin Invitation:** An admin must first invite a user to grant them the permission to register on the system. This process involves specifying the user’s email and role (either `USER` or `ADMIN`).

**2. User Registration:** After receiving an invitation, the user can complete their registration by providing additional details such as their first name, last name, email, phone number, and password. Upon successful registration, a JWT token is issued for authentication.

### 1. Invite User

**Endpoint:** `/admin/invite`  
**Method:** `POST`  
**Description:** Allows an admin to invite a new user to the system.

**Request Body:**

``` json
{
  "email": "string",
  "permission": "ADMIN or USER"  
}
```

- `email`: The email address of the user to be invited. It must be in a valid email format, such as `user@example.com`.
- `permission`: The permission level assigned to the user. It must be either `ADMIN` or `USER`.

**Response Body:**

``` json
{
  "userId": 1,
  "email": "string",
  "permission": "ADMIN or USER"
}
```

- `userId`: The unique identifier assigned to the newly created user.
- `email`: The email address of the invited user.
- `permission`: The permission level assigned to the user (`ADMIN` or `USER`).

**Flow:**
1. Admin sends an invitation request with the user's email and permission.
2. The system validates the email format.
3. If the email already exists, an error is thrown.
4. A new user is created with the provided email and permission.
5. An invitation email is sent to the user.
6. The response includes the `userId`, `email`, and `permission`.

### 2. Register User

**Endpoint:** `/auth/register`  
**Method:** `POST`  
**Description:** Allows a user to complete their registration after receiving an invitation.

**Request Body:**

``` json
{
  "firstName": "string", 
  "lastName": "string",
  "email": "string",
  "phoneNumber": "string",  
  "password": "string" 
}
```

- `firstName`: The first name of the user. It must be a non-blank string with a maximum length of 50 characters.
- `lastName`: The last name of the user. It must be a non-blank string with a maximum length of 50 characters.
- `email`: The email address of the user. It must be in a valid email format, such as `user@example.com`.
- `phoneNumber`: The phone number of the user. It must be in the format of "0" followed by 9 to 10 digits, e.g., `07123456789`.
- `password`: The password for the user. It must include at least one lowercase letter, one uppercase letter, one digit, one special character, and be 8 to 16 characters long.

**Response:**

``` json
{
  "token": "string",
  "userId": 1,
  "firstName": "string",
  "lastName": "string",
  "email": "string",
  "phoneNumber": "string",
  "userInfoId": 1,
  "permission": "ADMIN or USER",
  "enabled": true
}
```

- `userId`: The unique identifier of the user.
- `firstName`: The user's first name.
- `lastName`: The user's last name.
- `email`: The user's email address.
- `phoneNumber`: The user's phone number.
- `userInfoId`: The unique identifier for the user's additional information.
- `permission`: The permission level assigned to the user (`ADMIN` or `USER`).
- `enabled`: Indicates whether the user is enabled (`true` or `false`).

**Flow:**

1. User submits registration details.
2. The system checks if the email exists in the database.
3. Password is encoded using bcrypt.
4. If the email does not exist, an error is thrown.
5. The user is saved with the provided information.
6. A JWT token is generated and returned with the registration response.


# Testing

## Overview
- **Invitation Phase:**

    - **Valid Invitation:** Test valid invitation creation.
    - **Invalid Email Format:** Test invalid email format during invitation.
    - **Existing Email:** Test inviting an already existing email.
    - **Invalid Permission:** Test invalid permission value during invitation.
    - **Missing Email:** Test missing email field during invitation.
    - **Missing Permission:** Test missing permission field during invitation.

- **Registration Phase:**    
    - **Valid Registration:** Test valid registration with all required fields.
    - **Invalid Email Format:** Test registration with an invalid email format.
    - **Invalid Phone Number:** Test registration with an invalid phone number.
    - **Invalid Password Format:** Test registration with an invalid password format.
    - **Uninvited User:** Test registration of a user who hasn’t been invited.
    - **Missing First Name:** Test missing first name during registration.
    - **Missing Last Name:** Test missing last name during registration.
    - **Missing Email:** Test missing email field during registration.
    - **Missing Phone Number:** Test missing phone number during registration.
    - **Missing Password:** Test missing password during registration.

