# Logical View of the 4+1 Model for a Banking Application

```mermaid
classDiagram
    class Customer {
        +String customerID
        +String name
        +String address
        +String phoneNumber
        +createAccount(): Account
        +login(): void
        +logout(): void
    }

    class Account {
        +String accountNumber
        +double balance
        +deposit(amount: double): void
        +withdraw(amount: double): void
        +getBalance(): double
    }

    class Transaction {
        +String transactionID
        +Date transactionDate
        +double amount
        +String type
        +execute(): void
    }

    class BankingService {
        +createAccount(customer: Customer): Account
        +performTransaction(account: Account, transaction: Transaction): void
        +getAccountDetails(accountNumber: String): Account
        +login(customerID: String, password: String): Boolean
        +logout(customerID: String): void
    }

    Customer "1" -- "*" Account : "owns >"
    Account "1" -- "*" Transaction : "records >"
    BankingService "1" -- "*" Account : "manages >"
    BankingService "1" -- "*" Transaction : "processes >"
    BankingService "1" -- "*" Customer : "services >"
    Customer "1" -- "1" BankingService : "interacts >"
