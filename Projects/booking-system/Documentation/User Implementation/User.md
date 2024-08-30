The User Controller provides a set of features that allow users to manage their own accounts. These endpoints utilize Spring Security's authenticated user mechanism, which extracts the user ID directly from the authentication context. This design ensures that users do not need to provide their user ID in the requests, ensuring a user cannot access/edit another user's data.

## 1. Get User
**Endpoint:** `/user`  
**Method:** `GET`  
**Description:** Retrieves the profile of the currently logged-in user.

**Response Body:**
``` json
{
  "userId": 1,
  "firstName": "string",
  "lastName": "string",
  "email": "string",
  "phoneNumber": "string",
  "enabled": true,
  "permission": "ADMIN or USER"
}
```

- `userId`: The unique identifier of the user.
- `firstName`: The user's first name.
- `lastName`: The user's last name.
- `email`: The user's email address.
- `phoneNumber`: The user's phone number.
- `enabled`: Indicates if the user account is active (`true` or `false`).
- `permission`: The user's permission level (`ADMIN` or `USER`).

**Response Code:**

- `200 OK`: The user profile was successfully retrieved.

**Flow:**
1. The system retrieves the currently logged-in user's ID from the authentication context.
2. The User Profile Service is invoked using the user ID to fetch both user and user info details.
3. The combined information is returned as the user profile.


## 2. Update User Profile
**Endpoint:** `/user`  
**Method:** `PUT`  
**Description:** Allows a user to update their own email and password. Both fields are optional, allowing users to update one or both fields as needed.

**Request Body:**
``` json
{
  "email": "user@example.com",
  "password": "Password1!"
}
```

- `email`: The user's new email address. Must be in a valid email format, such as `example@domain.com`.
- `password`: The user's new password. Must have at least one special character, one uppercase letter, one lowercase letter, and one number, with a length between 8-16 characters.

Response Body:

``` JSON
{
  "userId": 1,
  "firstName": "string",
  "lastName": "string",
  "email": "user@example.com",
  "phoneNumber": "07123456789",
  "enabled": true,
  "permission": "USER"
}
```

- `userId`: The unique identifier of the user.
- `firstName`: The user's first name.
- `lastName`: The user's last name.
- `email`: The updated or existing email address.
- `phoneNumber`: The user's phone number.
- `enabled`: Indicates if the user account is active.
- `permission`: The user's permission level.


**Flow:**
1. The system retrieves the current user from the authentication context.
2. If an `email` is provided, it updates the user's email.
3. If a `password` is provided, it updates the user's password.
4. The updated user profile is returned.

**Response Code:**
- `200 OK`: The user profile was successfully updated.
- `400 Bad Request`: The request body contains invalid data (e.g., incorrect email format, password requirements not met).

## 3. Disable User
**Endpoint:** `/user/disable`  
**Method:** `PUT`  
**Description:** Allows a user to disable their own account. Once disabled, the user will need to contact an admin to reactivate the account.

**Flow:**
1. The system retrieves the current user from the authentication context.
2. The user's `enabled` status is set to `false`.
3. The system should also disable any active bookings associated with the user (functionality coming soon).

**Response Code:**

- `204 No Content`: The user account was successfully disabled.