# 📦 Domain Layer - Personal Finance Management App

The **Domain Layer** is the heart of the system. It encapsulates core business logic and rules for managing personal finances. All behaviors, validations, and constraints are represented through entities, aggregates, value objects, services, and interfaces.

---

## 🔧 Responsibilities

- Define core entities such as Wallets, Transactions, Budgets, and Goals
- Implement business rules like budget enforcement, balance tracking, and recurring transactions
- Remain independent of infrastructure (no database code here)
- Express **Ubiquitous Language** shared with stakeholders

---

## 🏗️ Folder Structure

```text
Domain/
├── Entities/
│   ├── User.cs
│   ├── Wallet.cs
│   ├── Transaction.cs
│   ├── Category.cs
│   └── Budget.cs
│
├── ValueObjects/
│   ├── Money.cs
│   ├── Currency.cs
│   ├── TimeRange.cs
│   └── TransactionNote.cs
│
├── Aggregates/
│   └── WalletAggregate.cs
│
├── Services/
│   ├── BudgetCalculatorService.cs
│   └── GoalTrackingService.cs
│
├── Interfaces/
│   ├── IWalletRepository.cs
│   ├── ITransactionRepository.cs
│   └── IBudgetRepository.cs
│
├── Specifications/
│   ├── TransactionsByDateRangeSpec.cs
│   └── BudgetExceededSpec.cs
│
├── Events/
│   ├── TransactionAddedEvent.cs
│   └── BudgetExceededEvent.cs
│
├── Exceptions/
│   ├── InsufficientBalanceException.cs
│   └── InvalidCategoryException.cs
│
└── Guards/
    └── WalletGuards.cs
```

---

## 🧠 Core Business Concepts

### ✅ Entities

- `User`: Basic identity info, linked to wallets
- `Wallet`: Holds balance, list of transactions, tied to a user
- `Transaction`: Represents income or expense, with category and timestamp
- `Budget`: Spending limits per category and period
- `Category`: Classifies types of income/expense

### ✅ Value Objects

- `Money`: Amount and currency, immutable and comparable
- `Currency`: Supports multi-currency systems
- `TimeRange`: Used for recurring payments or budget periods

### ✅ Aggregates

- `WalletAggregate`: Root entity that owns all transactions and governs their rules (e.g. balance update, budget enforcement)

### ✅ Domain Services

- `BudgetCalculatorService`: Computes remaining budget across categories
- `GoalTrackingService`: Evaluates goal progress based on transaction patterns

### ✅ Specifications

- `TransactionsByDateRangeSpec`: Filter transactions within a period
- `BudgetExceededSpec`: Check if a new transaction exceeds budget limits

### ✅ Domain Events

- `TransactionAddedEvent`: Fired when a new transaction is recorded
- `BudgetExceededEvent`: Alerts the system or parent app when a user overspends

### ✅ Custom Exceptions

- `InsufficientBalanceException`: When user tries to overspend
- `InvalidCategoryException`: Category not applicable to transaction type

### ✅ Guards

- Used to enforce pre-conditions (e.g. wallet must exist, amount must be positive)

---

## 🧭 Notes

- This layer must not depend on other layers (like Infrastructure or Application)
- All logic must be unit-testable and pure
- Design should reflect real-world business decisions and user needs

---
