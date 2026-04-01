# JavaAssignment5

# Banking System Application (Java – Inheritance & Exception Handling)

## Overview

This project is a **Java-based Banking System** designed to demonstrate key object-oriented programming concepts such as **inheritance, method overriding, polymorphism, and exception handling**.

The system models different types of bank accounts, including **Savings Accounts** and **Current Accounts**, each with its own rules for withdrawals and balance management. A custom exception is used to enforce business rules and ensure data integrity.

---

## Features

* Create different types of bank accounts:

  * Savings Account
  * Current Account
  * Generic Bank Account
* Perform deposit operations on all account types
* Perform withdrawal operations with account-specific rules
* Apply interest to savings accounts
* Support overdraft facility for current accounts
* Store multiple accounts using `ArrayList`
* Handle invalid operations using custom exceptions

---

## Project Structure

### 1. BankingException Class

A custom checked exception that extends `Exception`.

Purpose:

* Enforces business rules such as:

  * Invalid account details
  * Negative balances
  * Invalid transactions
* Provides meaningful error messages

---

### 2. BankAccount Class (Base Class)

Represents a generic bank account.

#### Data Members

* `accountNo` – unique account number
* `holderName` – account holder name
* `balance` – current account balance

#### Methods

* `deposit(double amount)` – adds money to the account
* `withdraw(double amount)` – withdraws money with basic validation
* `getAccountType()` – returns account type (can be overridden)
* `summary()` – returns formatted account details

---

### 3. SavingsAccount Class (Derived Class)

Extends `BankAccount`.

#### Additional Attributes

* `minBalance` – minimum balance to maintain
* `interestRate` – annual interest rate

#### Features

* Overrides `withdraw()` to ensure minimum balance is maintained
* Adds `applyAnnualInterest()` method to update balance

---

### 4. CurrentAccount Class (Derived Class)

Extends `BankAccount`.

#### Additional Attribute

* `overdraftLimit` – allowed negative balance limit

#### Features

* Overrides `withdraw()` to allow withdrawals beyond balance up to overdraft limit

---

### 5. BankingSimpleDemo Class (Main Class)

Acts as the entry point of the application.

Responsibilities:

* Creates different types of accounts
* Stores them in an `ArrayList`
* Performs deposit and withdrawal operations
* Demonstrates polymorphism and method overriding
* Displays account summaries

---

## Key Concepts Demonstrated

* Inheritance (Base class → Derived classes)
* Method Overriding
* Polymorphism (using base class references)
* Encapsulation
* Custom Exception Handling
* Collections (`ArrayList`)
* Business Rule Validation

---

## Application Workflow

1. Create multiple account objects (Savings, Current, Generic).
2. Store them in a collection.
3. Perform deposit operations on all accounts.
4. Perform withdrawal operations based on account type rules:

   * Savings: must maintain minimum balance
   * Current: can use overdraft
   * Generic: standard withdrawal
5. Display account summaries before and after transactions.
6. Handle errors using custom exceptions.

---

## How to Run the Program

### Prerequisites

* Java Development Kit (JDK) installed
* Terminal or Command Prompt

### Steps

1. Compile the program:

```
javac BankingSimpleDemo.java
```

2. Run the program:

```
java BankingSimpleDemo
```

---

## Sample Output

```
---- Initial State ----
[SAVINGS] AccNo=SA-101, Holder=Ayaan, Balance=5000.00
[CURRENT] AccNo=CA-201, Holder=Isha, Balance=2000.00
[GENERIC] AccNo=BA-301, Holder=Rahul, Balance=1500.00

---- Deposit 1000 in all accounts ----
...

---- Withdrawals (shows overriding rules) ----
...

```

---

## Exception Handling Rules

The program throws a `BankingException` in cases such as:

* Empty account number or holder name
* Negative opening balance
* Invalid deposit or withdrawal amounts
* Withdrawal violating:

  * Minimum balance (Savings Account)
  * Overdraft limit (Current Account)

---


