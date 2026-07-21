# Customer Communication System - Unit Testing with NUnit and Moq

## Project Overview

This project demonstrates **Unit Testing using NUnit and Moq** in C#. The main objective is to test the email communication functionality without sending real emails by using **Mocking** and **Dependency Injection (DI)**.

Instead of connecting to an actual SMTP mail server during testing, a mock object is created for the mail service, allowing fast, reliable, and isolated unit tests.

---

## Objectives

- Understand the concept of Mocking in Unit Testing.
- Learn how Dependency Injection improves testability.
- Create testable code using Constructor Injection.
- Use the Moq framework to create mock objects.
- Write and execute unit test cases using NUnit.
- Verify application behavior without accessing external services.

---

## Technologies Used

- C#
- .NET
- NUnit
- Moq
- Visual Studio
- Git & GitHub

---

## Project Structure

```
CustomerCommunicationSolution
│
├── CustomerCommLib
│   ├── IMailSender.cs
│   ├── MailSender.cs
│   ├── CustomerComm.cs
│
├── CustomerComm.Tests
│   └── UnitTest1.cs
│
└── CustomerCommLib.sln
```

---

## Project Description

### 1. IMailSender Interface

Defines the contract for sending emails.

```csharp
bool SendMail(string toAddress, string message);
```

---

### 2. MailSender Class

Implements the `IMailSender` interface.

Normally this class sends emails using SMTP. During unit testing, this implementation is **not executed** because it is replaced by a mock object.

---

### 3. CustomerComm Class

This is the class under test.

It receives an `IMailSender` object through **Constructor Dependency Injection**.

```csharp
public CustomerComm(IMailSender mailSender)
{
    _mailSender = mailSender;
}
```

The `SendMailToCustomer()` method calls the `SendMail()` method to send an email.

---

### 4. Unit Testing with NUnit

The test project contains unit tests that verify the functionality of `CustomerComm`.

The test checks whether `SendMailToCustomer()` returns `true`.

---

### 5. Mocking with Moq

A mock object is created instead of using the real `MailSender`.

```csharp
var mockMailSender = new Mock<IMailSender>();

mockMailSender
    .Setup(x => x.SendMail(It.IsAny<string>(), It.IsAny<string>()))
    .Returns(true);
```

This allows testing without connecting to an SMTP server or sending real emails.

---

## Key Concepts Demonstrated

- Unit Testing
- Mocking
- Dependency Injection
- Constructor Injection
- Interfaces
- Loose Coupling
- Test Isolation
- Moq Framework
- NUnit Framework

---

## Test Result

The unit test was executed successfully.

```
Build Status : Success
Tests Executed : 1
Tests Passed : 1
Tests Failed : 0
```

---

## Advantages of Mocking

- No dependency on external SMTP server
- Faster test execution
- Reliable and repeatable tests
- Better code maintainability
- Supports Test-Driven Development (TDD)

---

## Learning Outcome

Through this project, I learned:

- How to write testable code.
- How Dependency Injection improves application design.
- How to create mock objects using Moq.
- How to write unit tests using NUnit.
- How to isolate external dependencies during testing.
- How to verify application behavior without performing real operations.

---

## Conclusion

This project successfully demonstrates the implementation of **Unit Testing using NUnit and Moq**. By using Dependency Injection and Mocking, the application becomes more maintainable, loosely coupled, and easier to test without relying on external services such as an SMTP mail server.

---

## Author

**Name:** Madhuri Reddy 
**Technology:** C#, NUnit, Moq, Dependency Injection  
**Purpose:** Cognizant Digital Nurture 5.0 - Deep Skilling Assignment
