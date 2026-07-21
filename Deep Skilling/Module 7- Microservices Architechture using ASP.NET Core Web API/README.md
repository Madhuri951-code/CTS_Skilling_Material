# Microservices
# Authentication and Authorization using JWT in ASP.NET Core Web API

## Aim

To implement Authentication and Authorization in ASP.NET Core Web API Microservices using JSON Web Token (JWT).

---

# Objective

- Implement JWT Authentication.
- Generate JWT Token after successful login.
- Secure API endpoints using JWT.
- Implement Role-Based Authorization.
- Validate expired JWT tokens.
- Handle unauthorized requests.

---

# Software Requirements

- Visual Studio 2022
- .NET 8 Web API
- Swagger UI
- Postman
- ASP.NET Core
- JWT Bearer Authentication Package

---

# NuGet Packages Used

```
Microsoft.AspNetCore.Authentication.JwtBearer
Swashbuckle.AspNetCore
Microsoft.IdentityModel.Tokens
System.IdentityModel.Tokens.Jwt
```

---

# Project Structure

```
MicroserviceAuth
│
├── Controllers
│   ├── AuthController.cs
│   ├── SecureController.cs
│   ├── AdminController.cs
│
├── Models
│   ├── LoginModel.cs
│   ├── User.cs
│
├── Program.cs
├── appsettings.json
└── README.md
```

---

# appsettings.json

Contains JWT Configuration.

```json
{
  "Jwt": {
    "Key": "ThisIsASecretKeyForJwtToken1234567890",
    "Issuer": "MyAuthServer",
    "Audience": "MyApiUsers",
    "DurationInMinutes": 60
  }
}
```

---

# Program.cs

Configured

- JWT Authentication
- JWT Validation
- Authorization
- Swagger
- Token Expiry Validation

---

# Login Credentials

```
Username : admin

Password : admin123
```

---

# Question 1

## Implement JWT Authentication

### Steps

1. Created ASP.NET Core Web API project.
2. Installed JWT Authentication package.
3. Created LoginModel.
4. Created User model.
5. Implemented AuthController.
6. Generated JWT Token after successful login.

### API

```
POST
/api/Auth/login
```

### Request

```json
{
    "username":"admin",
    "password":"admin123"
}
```

### Response

```json
{
    "token":"eyJhbGc........"
}
```

---

# Question 2

## Secure API using JWT

Created

```
SecureController
```

Protected API

```
GET
/api/Secure/data
```

Added

```csharp
[Authorize]
```

### Without Token

```
401 Unauthorized
```

### With Valid Token

```
This is protected data.
```

---

# Question 3

## Role Based Authorization

Created

```
AdminController
```

Added

```csharp
[Authorize(Roles="Admin")]
```

### API

```
GET
/api/Admin/dashboard
```

### Output

```
Welcome to the Admin Dashboard.
```

---

# Question 4

## Token Expiry Validation

Configured JWT Bearer Events.

```csharp
OnAuthenticationFailed
```

Added Response Header

```
Token-Expired : true
```

### Output

```
401 Unauthorized
```

when expired token is used.

---

# JWT Flow

```
User Login
      │
      ▼
AuthController
      │
      ▼
Validate Credentials
      │
      ▼
Generate JWT Token
      │
      ▼
Client Receives Token
      │
      ▼
Client Sends Token
      │
      ▼
JWT Middleware
      │
      ▼
Validate Token
      │
      ▼
Authorized API Access
```

---

# Testing

## Using Swagger

1. Run the project.
2. Open Swagger.
3. Login using username and password.
4. Copy JWT Token.
5. Click Authorize.
6. Paste

```
Bearer <JWT Token>
```

7. Execute Secure APIs.

---

## Using Postman

### Login

```
POST
https://localhost:7074/api/Auth/login
```

### Body

```json
{
"username":"admin",
"password":"admin123"
}
```

Copy Token.

---

### Secure API

```
GET
/api/Secure/data
```

Authorization

```
Bearer Token
```

Paste JWT Token.

---

### Admin API

```
GET
/api/Admin/dashboard
```

Authorization

```
Bearer Token
```

---

# Output

## Login

JWT Token generated successfully.

## Secure API

```
This is protected data.
```

## Admin API

```
Welcome to the Admin Dashboard.
```

## Expired Token

```
401 Unauthorized
```

Header

```
Token-Expired : true
```

---

# Applications

- Banking Systems
- Healthcare Applications
- E-Commerce Websites
- Cloud Microservices
- Enterprise Applications
- REST APIs

---

# Advantages

- Secure Authentication
- Stateless Authentication
- Fast Validation
- Easy Integration
- Supports Role-Based Access
- Suitable for Microservices

---

# Disadvantages

- Token cannot be modified after generation.
- Large payload increases token size.
- Token revocation is difficult.
- Expired tokens require regeneration.

---

# Result

Successfully implemented Authentication and Authorization in ASP.NET Core Web API using JWT. The application generates JWT tokens, secures API endpoints, supports role-based authorization, validates token expiry, and handles unauthorized access successfully.
