# MWS Project Task Breakdown Rules

## Purpose
This document provides guidelines for breaking down technical design documents into actionable, granular tasks for the Medical Warehouse System (MWS) project, ensuring consistency and clarity in task management.

## General Principles

### 1. Task Granularity
- Tasks should be small and focused, typically completable within 2-4 hours.
- Break down complex tasks into smaller, manageable subtasks.
- Ensure each task represents a discrete, implementable unit of work.

### 2. Layer-Specific Considerations
When breaking down tasks, consider the project's 3-layer architecture:

#### API Layer Tasks
- Focus on:
  - Controller implementations
  - Endpoint definitions
  - Request/response mapping
  - Authentication and authorization checks
  - Middleware configurations

#### Business Logic Layer (BLL) Tasks
- Emphasize:
  - Service method implementations
  - Business rule validations
  - DTO mappings
  - Custom exception handling
  - Interface implementations
  - Validation rule creation

#### Data Access Layer (DAL) Tasks
- Concentrate on:
  - Entity definitions
  - Repository method implementations
  - Database configuration
  - Migration scripts
  - Unit of Work pattern implementation

### 3. Task Categorization
Organize tasks into clear categories:
- Database
- API Endpoints
- Business Logic
- Validation
- Testing
- Documentation

### 4. Dependency Tracking
- Explicitly note task dependencies
- Ensure tasks are ordered logically
- Use clear markers like "(depends on Task X)" when necessary

## Task Breakdown Template

### Task Format
```markdown
- [ ] Layer: Specific Component: Task Description
    - [ ] Subtask 1
    - [ ] Subtask 2 (optional)
```

### Example Categories

#### Database Tasks
- [ ] Create database migration
- [ ] Define entity configurations
- [ ] Update database schema

#### API Tasks
- [ ] Implement controller endpoint
- [ ] Add authentication
- [ ] Configure middleware

#### Business Logic Tasks
- [ ] Implement service method
- [ ] Create validation rules
- [ ] Define business logic

#### Testing Tasks
- [ ] Write unit tests
- [ ] Create integration tests
- [ ] Perform edge case testing

#### Documentation Tasks
- [ ] Update API documentation
- [ ] Create usage examples
- [ ] Write technical specifications

## Best Practices
1. Use clear, action-oriented language
2. Include context in task descriptions
3. Break down complex tasks into manageable subtasks
4. Prioritize tasks when possible
5. Ensure all aspects of the design are covered

## Common Task Verbs
- Create
- Implement
- Update
- Refactor
- Configure
- Define
- Test
- Document
- Validate

## Validation Checklist
Before finalizing task breakdown:
- [ ] All design aspects are covered
- [ ] Tasks are clear and actionable
- [ ] Dependencies are identified
- [ ] Tasks are appropriately sized
- [ ] Layer responsibilities are respected

## Open Questions Handling
- If design document has open questions, create specific tasks to:
  - Research potential solutions
  - Consult with team members
  - Document findings
  - Make design decisions

## Continuous Improvement
- Regularly review and refine task breakdown approach
- Gather feedback from development team
- Adjust guidelines based on project complexity and team needs
