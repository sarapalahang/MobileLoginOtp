# MobileLoginOtp

A standalone .NET application for phone-number OTP authentication and account workflows. The solution includes an ASP.NET Core MVC web app, a companion Web API, and a WinForms project.

## Features

- Phone-number sign-in and verification with SMS OTP
- Email sign-in, account recovery, and profile completion workflows
- User, role, and access management
- Payment initiation and callback verification
- HR assistant pages with an AI service integration
- SQL Server persistence through Entity Framework Core

## Technology

- C# and .NET 10
- ASP.NET Core MVC and Web API
- Entity Framework Core and SQL Server
- Cookie authentication and session state

## Solution layout

```text
MobileLoginOtp.slnx
MobileLoginOtp.Api/               Companion API
src/MobileLoginOtp/               ASP.NET Core MVC web application
src/MobileLoginOtp.Application/   Application services and contracts
src/MobileLoginOtp.Domain/        Domain entities and interfaces
src/MobileLoginOtp.Infrastructure/Database and repository implementations
src/MobileLoginOtp.WinForms/      WinForms client project
```

## Run locally

### Requirements

- .NET 10 SDK
- SQL Server
- Credentials for the external services you want to use (SMS, email, payments, and AI)

### Configure

1. Copy `src/MobileLoginOtp/appsettings.example.json` to `src/MobileLoginOtp/appsettings.json`.
2. Set the SQL Server connection string and the required service credentials in the local file.
3. Keep real credentials out of commits. The local settings file is ignored by Git.

### Start the web app

```powershell
dotnet restore MobileLoginOtp.slnx
dotnet run --project src/MobileLoginOtp/MobileLoginOtp.csproj
```

The web app applies its Entity Framework migrations at startup. Make sure the configured SQL Server is available.

### Start the API

```powershell
dotnet run --project MobileLoginOtp.Api/MobileLoginOtp.Api.csproj
```

Swagger is enabled for the API in the Development environment.
