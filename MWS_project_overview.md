# MWS Project Overview

## Project Structure
The project follows 3 Layer Architecture principles with clear separation of concerns:

```
medical-warehouse-be2/
├── API/                     # API project - Entry point of the application
│   ├── Controllers/         # Handles HTTP requests (CQRS if needed)
│   ├── Middlewares/         # Common middleware (logging, exception handling, authentication...)
│   ├── appsettings.json     # Application settings
│   ├── Program.cs           # Application entry point
│
├── BLL/                     # Business Logic Layer - Core business rules
│   ├── Interfaces/          # Interfaces for services (Repository, UnitOfWork)
│   ├── Services/            # Business services (implements Interfaces)
│   ├── Mappers/             # Converts between Entity ↔ DTO
│   ├── Utils/               # Utility functions used in business logic
│   ├── Exceptions/          # Custom exceptions
│   ├── Rules/               # Core business rules
│   ├── Validators/          # Validation rules (FluentValidation)
│   └── ValueObjects/        # Domain Value Objects
│
├── DAL/                     # Data Access Layer - Database interactions
│   ├── Entities/            # Database entities (EF Core)
│   ├── Configurations/      # Fluent API configurations for entities
│   ├── Context/             # DbContext and migration scripts
│   ├── Repositories/        # Repository pattern for data access
│   ├── UnitOfWork/          # Unit of Work pattern for transaction management
├── Common/                  # Shared components across layers
│   ├── DTOs/                # Data Transfer Objects (request/response models)
│   ├── Enums/               # Common enums
│   ├── Constants/           # Global constants
│   ├── Helpers/             # Helper functions
│   ├── Extensions/          # Extension methods
├── .gitignore               # Git ignore file
├── README.md                # Project description
└── API.sln      # Solution file for the entire project
```



## Infrastructure Highlights

1. **Persistence**:
   - Entity Framework Core with MySQL
   - Repository pattern implementation
   
