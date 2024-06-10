# Logical View of the 4+1 Model for a Banking Application

```mermaid
classDiagram
    class Customer {
        +String customerID
        +String name
        +String address
        +String phoneNumber
        +createAccount()
        +login()
        +logout()
    }

    class Account {
        +String accountNumber
        +double balance
        +deposit(amount: double)
        +withdraw(amount: double)
        +getBalance(): double
    }

    class Transaction {
        +String transactionID
        +Date transactionDate
        +double amount
        +String type
        +execute()
    }

    class BankingService {
        +createAccount(customer: Customer): Account
        +performTransaction(account: Account, transaction: Transaction)
        +getAccountDetails(accountNumber: String): Account
    }

    Customer "1" -- "*" Account : owns >
    Account "1" -- "*" Transaction : records >
    BankingService "1" -- "*" Account : manages >
    BankingService "1" -- "*" Transaction : processes >
    Customer "1" -- "1" BankingService : interacts >
