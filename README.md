# Repository Pattern with Unit of Work — .NET

A **.NET Web API** demonstrating the **Repository Pattern** and **Unit of Work** design pattern using Entity Framework Core — applied to a simple books and authors domain.

## What it does

This project is a practical reference implementation showing how to abstract data access behind repository interfaces and coordinate multiple repository operations through a single Unit of Work. It's a clean architectural pattern commonly used in production .NET applications.

## Tech Stack

- **ASP.NET Core Web API** (.NET)
- **Entity Framework Core** — Code-First with SQL Server
- **Repository Pattern + Unit of Work**

## Project Structure

| Project | Purpose |
|---|---|
| `RepositoryPatternWithUOW.Api` | Web API controllers and entry point |
| `RepositoryPatternWithUOW.Core` | Interfaces (`IBaseRepository`, `IUnitOfWork`), domain models |
| `RepositoryPatternWithUOW.EF` | EF Core implementations of repositories and UoW |

## Key Concepts Demonstrated

- `IBaseRepository<T>` — generic CRUD interface
- `IBooksRepository` — domain-specific extension of the base repository
- `IUnitOfWork` — aggregates all repositories and exposes `CompleteAsync()`
- `OrderBy` constants for consistent query ordering

## Getting Started

1. Set your connection string in `appsettings.json`.
2. Apply migrations:
   ```bash
   dotnet ef database update --project RepositoryPatternWithUOW.EF --startup-project RepositoryPatternWithUOW.Api
   ```
3. Run the API:
   ```bash
   dotnet run --project RepositoryPatternWithUOW.Api
   ```
