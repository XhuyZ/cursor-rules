# 🧠 Rules for Project Core (Domain Layer) in Clean Architecture

## 🎯 Purpose of the Domain Layer

- It is the **heart** of the system.
- Contains only **pure business logic**.
- **No dependencies** on any other layers such as database, UI, or external frameworks.
- Easy to test, maintain, and clearly reflects real-world business rules.

---

## 📁 Folder Structure in Domain

```
Domain/
├── Entities/
├── Aggregates/
├── ValueObjects/
├── Interfaces/
├── Repositories/
├── DomainServices/
├── Specifications/
├── Events/
│   ├── DomainEvents/
│   └── EventHandlers/
├── Exceptions/
├── Guards/
├── Validators/
```

---

## ✅ Core Rules

### 1. **Do not use EF Core or any persistence library**
> The domain must be completely independent of the database.

### 2. **Avoid using static classes, `DateTime.Now`, or `Guid.NewGuid()` directly**
> Instead, inject via `ISystemClock`, `IGuidGenerator` for better testability.

### 3. **All business logic resides in Entities or Domain Services**
- Entity: logic related to itself
- Domain Service: logic involving multiple entities

### 4. **Only create Repository for Aggregate Roots**
> Do not create repositories for child entities inside aggregates.

### 5. **Use Value Objects for immutability and validation**
> E.g.: `Money`, `EmailAddress`, `PhoneNumber`, etc.

### 6. **Use Specification Pattern to encapsulate reusable business conditions**
> Enhances readability and testability.

### 7. **Use Domain Events to signal changes in the domain**
> E.g.: `OrderCreatedEvent` when an order is placed.

### 8. **Do not throw framework exceptions like `SqlException`, `DbUpdateException`**
> Use custom business exceptions in `Exceptions/`.

### 9. **No service implementations in Domain**
> All interfaces in `Interfaces/` are implemented in Infrastructure.

### 10. **No DI container or configurations in Domain**
> The domain is pure logic — it does not "run" directly.

---

## 📌 Extended Notes

| Component | Purpose |
|----------|---------|
| `Entities` | Represent core business objects |
| `Aggregates` | Consistency boundary and entry point |
| `ValueObjects` | Immutable, no identity |
| `Repositories` | Interface only, implemented elsewhere |
| `Specifications` | Reusable business rules |
| `Events` | Domain-level events |
| `Guards` | Guard clauses for validation |
| `Validators` | Validate business-specific rules |

---

## 🧪 Testing Suggestions

- Test Entity and Domain Service logic without touching the database
- Mock interfaces like `ISystemClock`, `IUserAccessor`, `IEmailSender`, etc.

---

## 🛑 Things You **Must Not** Do in Domain

| ❌ Don't | ✅ Do Instead |
|---------|---------------|
| Call DB, EF | Use repository interfaces |
| Call external APIs, send emails | Define interfaces like `IEmailSender` |
| Log directly | Use domain events if necessary |
| Access filesystem | Use `IFileAccessor` |
| Load config | Never |

---

## 📚 Summary

The Domain Layer is the most critical part of Clean Architecture. Everything else (UI, DB, API, logs...) **serves the domain**, not the other way around.

Writing a clean Domain layer is the foundation for a robust, scalable architecture 💪
