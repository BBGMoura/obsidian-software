**Admin Role**: The admin role has extended functionalities compared to a regular user. Access to these endpoints requires `ADMIN` permission.

### 1. Get User Profile

**Endpoint:** `/admin/user/{userId}`  
**Method:** `GET`  
**Description:** Retrieve a user profile by their unique ID.

**Path Variable:**
- `userId`: The unique identifier of the user whose profile is being retrieved.

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
- `permission`: The user's permission level (`ADMIN` or `USER`).
- `enabled`: Indicates if the user account is active (`true` or `false`).

**Response Code:**
- `200 OK`: The user profile was successfully retrieved.
- `404 Not Found`: The user with the specified `userId` does not exist.

**Flow:**

1. Admin sends a request to retrieve the profile of the user with the specified `userId`.
2. The system retrieves and returns the user's profile information. User profile is a DTO of both the User and UserInfo.


### 2. Get Users List

**Endpoint:** `/admin/users`  
**Method:** `GET`  
**Description:** Allows an admin to retrieve a paginated list of user profiles. The list is sorted alphabetically and paginated with default and configurable page sizes.

**Request Parameters:**

- `page`: The page number to retrieve. Default is `0`.
- `size`: The number of users per page. Default is `5`.

**Response Body:**
``` json
{
  "content": [
    {
      "userId": 1,
      "firstName": "string",
      "lastName": "string",
      "email": "string",
      "phoneNumber": "string",
      "status": true,
      "permission": "ADMIN or USER"
    },
    // More user profiles
  ],
  "pageable": {
    "sort": {
      "sorted": true,
      "unsorted": false,
      "empty": false
    },
    "pageNumber": 0,
    "pageSize": 5,
    "offset": 0,
    "unpaged": false,
    "paged": true
  },
  "totalElements": 50,
  "totalPages": 10,
  "size": 5,
  "number": 0,
  "sort": {
    "sorted": true,
    "unsorted": false,
    "empty": false
  },
  "numberOfElements": 5,
  "first": true,
  "last": false,
  "empty": false
}
```


### 3. Invite User

**Endpoint:** `/admin/invite`  
**Method:** `POST`  
**Description:** Allows an admin to invite a new user to the system. This process involves specifying the user’s email and role (either `USER` or `ADMIN`).

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

**Response Code:**

- `201 Created`: The user was successfully invited, and an invitation email was sent.
- `400 Bad Request`: Invalid email format or other input issues.

**Flow:**

1. Admin sends an invitation request with the user's email and permission.
2. The system validates the email format.
3. If the email already exists, an error is thrown.
4. A new user is created with the provided email and permission.
5. An invitation email is sent to the user.
6. The response includes the `userId`, `email`, and `permission`.


### 4. Update User Status

**Endpoint:** `/admin/user/{userId}/status`  
**Method:** `PUT`  
**Description:** Allows an admin to enable or disable a user. Disabling a user prevents them from logging in and sets their bookings to cancelled.

**Request Parameters:**

- `userId`: The unique identifier of the user whose status is to be updated.
- `enable`: A boolean indicating whether to enable (`true`) or disable (`false`) the user.

**Response Code:**

- `204 No Content`: The user status was successfully updated.
- `404 Not Found`: The user with the specified ID does not exist.
- `400 Bad Request`: Invalid status parameter.

**Flow:**

1. Admin sends a request to update the user's status with the user ID and status (enabled/disabled).
2. The system updates the user's status and handles associated effects (e.g., cancelling bookings).
3. ......
4. The response indicates success with no content.
