# Lab 1 – First ASP.NET Core Web API

## Title
First Web API using ASP.NET Core

---

# Objective

- Understand the basics of ASP.NET Core Web API.
- Learn how to create a Web API project.
- Execute the default GET API.
- Test the API using Swagger UI.

---

# Theory

## What is REST?

REST (Representational State Transfer) is an architectural style used for developing web services. REST APIs allow applications to communicate over HTTP using standard methods such as GET, POST, PUT, and DELETE.

### Features of REST

- Stateless communication
- Client-Server architecture
- Uniform Interface
- Resource-based URLs
- Supports multiple data formats like JSON and XML

---

## What is Web API?

A Web API is an application programming interface that allows different software applications to communicate over the internet using HTTP.

It receives requests from clients and sends responses in formats such as JSON or XML.

Example:

Client → Web API → Database

---

## What is a Microservice?

A Microservice is a small, independent service that performs one specific task.

Example:

- Student Service
- Employee Service
- Product Service

Each service works independently and communicates through APIs.

---

## Difference between Web Service and Web API

| Web Service | Web API |
|-------------|----------|
| Uses SOAP or REST | Mainly REST |
| Mostly XML | JSON or XML |
| Slower | Faster |
| More complex | Simpler |

---

## HTTP Request

An HTTP Request is sent by the client to the server asking for data or requesting an operation.

Example:

```
GET /WeatherForecast
```

---

## HTTP Response

The server sends back an HTTP Response containing:

- Status Code
- Headers
- Data (JSON)

Example:

```json
[
  {
    "date":"2026-07-15",
    "temperatureC":35,
    "summary":"Warm"
  }
]
```

---

## HTTP Action Verbs

| Verb | Purpose |
|-------|----------|
| GET | Retrieve data |
| POST | Insert new data |
| PUT | Update existing data |
| DELETE | Delete data |

---

## Common HTTP Status Codes

| Status Code | Meaning |
|-------------|----------|
| 200 OK | Request successful |
| 400 Bad Request | Invalid request |
| 401 Unauthorized | Authentication required |
| 500 Internal Server Error | Server error |




---

# Procedure

1. Open Visual Studio 2022.
2. Click **Create a new project**.
3. Select **ASP.NET Core Web API**.
4. Name the project **FirstWebAPI**.
5. Choose:
   - Framework: .NET 10 (LTS)
   - Authentication: None
   - Use Controllers ✓
   - Enable OpenAPI Support ✓
6. Click **Create**.
7. Build the project.
8. Run the application.
9. Swagger UI opens automatically.
10. Execute **GET /WeatherForecast**.
11. Verify the JSON response.

---

# Files Used

- Program.cs
- WeatherForecast.cs
- WeatherForecastController.cs
- appsettings.json
- launchSettings.json

---

# Output

Swagger UI was launched successfully.

Executing the **GET /WeatherForecast** endpoint returned the following JSON response.

```json
[
  {
    "date": "2026-07-15",
    "temperatureC": 37,
    "temperatureF": 98,
    "summary": "Bracing"
  }
]
```

---

# Result

Successfully created and executed the first ASP.NET Core Web API project using Visual Studio 2022. The default GET API was tested successfully through Swagger UI, and the JSON response was displayed.
