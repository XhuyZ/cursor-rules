# Medical Warehouse System (MWS) Implementation Rules

## Workflow Overview

### 1. Task Receiving and Preparation
- Receive a specific task from the project task breakdown checklist
- Receive corresponding Technical Design Document (TDD)
- Confirm task details and seek clarification if needed before implementation

### 2. Task Review Process
#### Document Review Checklist
- [ ] Carefully examine TDD sections:
  - [ ] Overview
  - [ ] Functional Requirements
  - [ ] Non-Functional Requirements
  - [ ] Technical Design Details
  - [ ] Potential Constraints or Limitations
- [ ] Understand task's relationship to broader system architecture
- [ ] Identify potential implementation challenges
- [ ] Ask clarifying questions about any ambiguous requirements

### 3. Implementation Guidelines

#### Architectural Principles
- Follow 3-Layer Architecture principles
- Adhere to Separation of Concerns
- Implement Domain-Driven Design (DDD) concepts
- Use CQRS pattern for complex operations

#### Coding Standards

##### General Conventions
- Use PascalCase for:
  - Class names
  - Public methods
  - Properties
- Use camelCase for:
  - Local variables
  - Method parameters
- Write clean, self-documenting code
- Minimize complexity
- Follow SOLID principles

##### Layer-Specific Guidelines

###### API Layer
- Use CQRS-based controllers
- Implement comprehensive input validation
- Use appropriate HTTP status codes
- Implement centralized error handling
- Secure endpoints with appropriate authentication/authorization

###### Business Logic Layer (BLL)
- Implement business rules and validations
- Use FluentValidation for input validation
- Create clear, focused service methods
- Utilize interfaces for dependency injection
- Handle domain-specific exceptions

###### Data Access Layer (DAL)
- Use Repository and Unit of Work patterns
- Implement efficient database queries
- Use Entity Framework Core best practices
- Create migration scripts for schema changes

#### Documentation Standards
- Include comprehensive XML documentation comments
- Document public methods with:
  ```csharp
  /// <summary>
  /// Brief method description.
  /// </summary>
  /// <param name="paramName">Parameter description.</param>
  /// <returns>Return value description.</returns>
  /// <exception cref="ExceptionType">Exception description.</exception>
  ```

#### Testing Requirements
- Write unit tests for:
  - Business logic
  - Service methods
  - Repository interactions
- Implement integration tests for critical paths
- Aim for high code coverage
- Use xUnit for testing framework

### 4. Checklist Management
- Mark tasks as complete using markdown syntax
  ```markdown
  - [x] Task Name: Detailed description (Completed)
  ```
- Only mark tasks complete after:
  - Full implementation
  - Code review
  - Successful testing

### 5. Commit Process
#### Conventional Commits Format
Use the following commit message prefixes:
- `feat:` New feature implementation
- `fix:` Bug fixes
- `docs:` Documentation updates
- `refactor:` Code restructuring
- `test:` Test-related changes
- `chore:` Maintenance tasks
- `perf:` Performance improvements
- `ci:` CI/CD pipeline modifications

### 6. External Service Interactions
- Use circuit breaker pattern for external calls
- Implement robust error handling
- Log all external service interactions
- Use dependency injection for service configurations

### 7. Performance and Security Considerations
- Optimize database queries
- Implement caching strategies
- Use asynchronous programming
- Validate and sanitize all inputs
- Follow OWASP security guidelines

### 8. Continuous Improvement
- Regularly review and refactor code
- Stay updated with .NET and C# best practices
- Participate in code reviews
- Provide constructive feedback

## Tooling and Environment

### Recommended Tools
- Visual Studio 2022
- Rider (alternative to Visual Studio)
- ReSharper for code quality
- Docker for containerization
- Postman for API testing

### Required NuGet Packages
- MediatR
- FluentValidation
- AutoMapper
- Serilog
- Entity Framework Core
- xUnit
- Moq

## Open Questions and Collaboration
- Encourage team communication
- Use pull requests for code reviews
- Document architectural decisions
- Maintain a living architecture document

## Exceptions and Special Cases
- If implementation deviates from TDD:
  1. Stop work immediately
  2. Communicate with team lead
  3. Update Technical Design Document
  4. Get approval before continuing

## Final Checklist Before Submission
- [ ] Code follows MWS coding standards
- [ ] All tests pass
- [ ] Documentation is complete
- [ ] Performance is optimized
- [ ] Security considerations are addressed
- [ ] Code is ready for review
