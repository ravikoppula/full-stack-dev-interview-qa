

# Object-Oriented Programming Concepts in C#

This README file provides an overview of the main Object-Oriented Programming (OOP) concepts with definitions and real-time examples, specifically tailored for a banking domain software developer.

## 1. Class
**Definition**: A class is a blueprint for creating objects. It defines properties (attributes) and methods (functions) that the objects created from the class will have.

**Real-Time Example**: In a banking system, a `CustomerAccount` class can be defined to represent customer accounts.

```csharp
public class CustomerAccount
{
    public string AccountNumber { get; set; }
    public string AccountHolder { get; set; }
    public double Balance { get; set; }

    public void Deposit(double amount)
    {
        Balance += amount;
    }
}
```

## 2. Object
**Definition**: An object is an instance of a class. It is the actual entity that contains the data and can perform the actions defined by the class.

**Real-Time Example**: Creating an object of the `CustomerAccount` class for a specific customer.

```csharp
CustomerAccount account = new CustomerAccount();
account.AccountNumber = "123456789";
account.AccountHolder = "Ravi";
account.Deposit(5000);
```

## 3. Interface
**Definition**: An interface is a contract that defines a set of methods and properties that implementing classes must provide. Interfaces only contain method declarations; the actual implementation is done in the classes that implement the interface.

**Real-Time Example**: In a banking system, an interface `IPaymentProcessor` can define methods for different payment processing methods like credit card, bank transfer, etc.

```csharp
public interface IPaymentProcessor
{
    void ProcessPayment(double amount);
}

public class CreditCardPayment : IPaymentProcessor
{
    public void ProcessPayment(double amount)
    {
        // Process credit card payment
    }
}

public class BankTransferPayment : IPaymentProcessor
{
    public void ProcessPayment(double amount)
    {
        // Process bank transfer payment
    }
}
```

## 4. Abstraction
**Definition**: Abstraction involves hiding the complex details of a system and exposing only the essential parts to the user.

**Real-Time Example**: In a banking application, the `LoanProcessingSystem` class can abstract the complexity of different loan processing algorithms.

```csharp
public abstract class LoanProcessingSystem
{
    public abstract void ProcessLoanApplication(string applicationId);
}
```

## 5. Encapsulation
**Definition**: Encapsulation is the technique of bundling the data (attributes) and methods (functions) that operate on the data into a single unit or class, and restricting access to some of the object's components.

**Real-Time Example**: The `Transaction` class encapsulates transaction details and only allows access through defined methods.

```csharp
public class Transaction
{
    private double amount;

    public void SetAmount(double value)
    {
        if (value > 0)
        {
            amount = value;
        }
    }

    public double GetAmount()
    {
        return amount;
    }
}
```

## 6. Inheritance
**Definition**: Inheritance allows a new class to inherit properties and methods from an existing class. This promotes code reusability.

**Real-Time Example**: In a banking application, a `SavingsAccount` class can inherit from a `BankAccount` base class.

```csharp
public class BankAccount
{
    public string AccountNumber { get; set; }
    public string AccountHolder { get; set; }

    public void Deposit(double amount)
    {
        // Deposit logic
    }
}

public class SavingsAccount : BankAccount
{
    public double InterestRate { get; set; }

    public void ApplyInterest()
    {
        // Apply interest logic
    }
}
```

## 7. Polymorphism
**Definition**: Polymorphism allows objects of different classes to be treated as objects of a common base class. It provides the ability to call the same method on different objects and have each object respond in its own way.

**Real-Time Example**: In a banking system, different types of accounts (e.g., `SavingsAccount`, `CurrentAccount`) might have their own implementations of the `CalculateInterest()` method.

```csharp
public class BankAccount
{
    public virtual void CalculateInterest()
    {
        // General interest calculation
    }
}

public class SavingsAccount : BankAccount
{
    public override void CalculateInterest()
    {
        // Savings account interest calculation
    }
}

public class CurrentAccount : BankAccount
{
    public override void CalculateInterest()
    {
        // Current account interest calculation
    }
}
```

## 8. Overloading
**Definition**: Overloading allows the creation of multiple methods with the same name but different parameters in the same class.

**Real-Time Example**: In a `Loan` class, you might have overloaded methods for calculating interest based on different parameters.

```csharp
public class Loan
{
    public double CalculateInterest(double principal, double rate)
    {
        return principal * rate;
    }

    public double CalculateInterest(double principal, double rate, int years)
    {
        return principal * rate * years;
    }
}
```

## 9. Overriding
**Definition**: Overriding allows a subclass to provide a specific implementation for a method that is already defined in its superclass.

**Real-Time Example**: In a `BankAccount` class, you might override the `Withdraw` method in a `SavingsAccount` subclass to add specific withdrawal rules.

```csharp
public class BankAccount
{
    public virtual void Withdraw(double amount)
    {
        // General withdrawal logic
    }
}

public class SavingsAccount : BankAccount
{
    public override void Withdraw(double amount)
    {
        // Specific withdrawal logic for savings accounts
    }
}
```

## 10. Constructor
**Definition**: A constructor is a special method that is automatically called when an object of a class is created. It is used to initialize the object.

**Real-Time Example**: When creating a new `Customer` in a banking system, a constructor can initialize the customer's data.

```csharp
public class Customer
{
    public string Name { get; }
    public string AccountNumber { get; }

    public Customer(string name, string accountNumber)
    {
        Name = name;
        AccountNumber = accountNumber;
    }
}
```

## 11. Destructor
**Definition**: A destructor is a method that is called when an object is destroyed. It is used to clean up resources.

**Real-Time Example**: In a banking system, a destructor could be used to close database connections when a `Transaction` object is destroyed.

```csharp
public class Transaction
{
    ~Transaction()
    {
        // Clean up resources
    }
}
```

## 12. Static
**Definition**: A static member (method, variable) belongs to the class rather than any specific instance, meaning it can be accessed without creating an object.

**Real-Time Example**: In a banking application, a static method might be used to calculate interest rates that apply to all accounts.

```csharp
public static class InterestCalculator
{
    public static double CalculateRate()
    {
        return 0.05; // Static interest rate
    }
}
```

---

This document provides an essential understanding of OOP concepts with practical examples, helping you in your development work within the banking domain.
