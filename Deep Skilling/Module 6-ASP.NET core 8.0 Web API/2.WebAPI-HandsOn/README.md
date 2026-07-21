# Lab 2 – ASP.NET Core Web API with Swagger and Postman

## Overview

In this experiment, an ASP.NET Core Web API project named **FirstWebAPI** was created using Visual Studio. The project was created using the **ASP.NET Core Web API** template with **Controllers** and **OpenAPI (Swagger)** support enabled.

After creating the project, the application was executed successfully. Swagger UI was automatically generated, which displayed the default **WeatherForecast** API. The GET endpoint of the WeatherForecast controller was tested using Swagger, and a JSON response was returned successfully.

The same API was then tested using **Postman** by sending a **GET** request to the local API URL. The response was verified, and the API returned the expected JSON data with **HTTP Status Code 200 (OK)**.

Next, a new controller named **EmployeeController** was created. Inside this controller, a **GET** action method was implemented to return a list of employee names.

The employee list used in the experiment was:

- John
- David
- Alice
- Jyothirmai Chapala

The newly created Employee API was tested using both **Swagger UI** and **Postman**, and the employee list was returned successfully in JSON format.

Finally, the route attribute of the Employee controller was modified from:

```csharp
[Route("[controller]")]
```

to

```csharp
[Route("Emp")]
```

After changing the route, the API endpoint changed from:

```
/Employee
```

to

```
/Emp
```

The modified endpoint was again tested using **Swagger** and **Postman**, and the API returned the expected employee list successfully.

## Result

The ASP.NET Core Web API was created and executed successfully. Swagger UI and Postman were used to test the API endpoints. A custom Employee API was implemented, its route was modified, and all API requests returned the expected JSON responses successfully.
