# Backend API Documentation

##  `/users/register` Endpoint

### Description

Register a new user by creating a user account with the provided information

### HTTP Method

`POST`

### Request Body

- `fullname` (object):
   - `firstname` (string, required): First name of the user (minimum 3 characters).
   - `lastname` (string, optional): Last name of the user (minimum 3 characters).
- `email` (string, required): Valid email address of the user.
- `password` (string, required): Password for the user account (minimum 6 characters).

#### Example Response

- `user` (object):
   - `fullname`(object).
      - `firstname` (string): First name of the user (minimum 3 characters).
      - `lastname` (string): Last name of the user (minimum 3 characters).
   - `email` (string): Valid email address of the user.
   - `password` (string): Password for the user account (minimum 6 characters).
- `token`(String): JWT Token

## `/users/login` Endpoint

### Description

Authenticate an existing user using their email and password.

### HTTP Method

`POST`

### Request Body

- `email` (string, required): Email address of the user.
- `password` (string, required): Password for the user account (minimum 6 characters).

#### Example Response

- `user` (object):
   - `fullname`(object).
      - `firstname` (string): First name of the user (minimum 3 characters).
      - `lastname` (string): Last name of the user (minimum 3 characters).
   - `email` (string): Valid email address of the user.
   - `password` (string): Password for the user account (minimum 6 characters).
- `token`(String): JWT Token

## `/users/profile` Endpoint

### Description

Retrieve the profile information of the authenticated user.

### HTTP Method

`GET`

### Authentication

Required a valid JWT token in the Authorization header: `Authorization:Bearer <token>`

#### Example Response

- `user` (object):
   - `fullname`(object).
      - `firstname` (string): First name of the user (minimum 3 characters).
      - `lastname` (string): Last name of the user (minimum 3 characters).
   - `email` (string): Valid email address of the user.



## `/users/logout` Endpoint

### Description

Logout the current user and blacklist the token provided in cookie or headers

### HTTP Method

`GET`

### Authentication

Required a valid JWT token in the Authorization header or cookie:

## `/captains/register` Endpoint

### Description

Register a new captain by creating a captain account with the provided information.

### HTTP Method

`POST`

### Request Body

- `fullname` (object):
   - `firstname` (string, required): First name of the captain (minimum 3 characters).
   - `lastname` (string, optional): Last name of the captain.
- `email` (string, required): Valid email address of the captain.
- `password` (string, required): Password for the captain account (minimum 6 characters).
- `vehicle` (object):
   - `color` (string, required): Color of the vehicle (minimum 3 characters).
   - `plate` (string, required): Plate number of the vehicle (minimum 3 characters).
   - `capacity` (number, required): Capacity of the vehicle (minimum 1).
   - `vehicleType` (string, required): Type of the vehicle (`car`, `motorcycle`, `auto`).

#### Example Response

- `captain` (object):
   - `fullname` (object):
      - `firstname` (string): First name of the captain.
      - `lastname` (string): Last name of the captain.
   - `email` (string): Email address of the captain.
   - `password` (string): User's password
   - `vehicle` (object):
      - `color` (string): Color of the vehicle.
      - `plate` (string): Plate number of the vehicle.
      - `capacity` (number): Capacity of the vehicle.
      - `vehicleType` (string): Type of the vehicle.
- `token` (string): JWT Token