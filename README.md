# Banking-System

6Banking system:

class Bank {
    String bankName;
    Account[] accounts;

    public Bank(String bankName, Account[] accounts) {
        this.bankName = bankName;
        this.accounts = accounts;
    }
}

class Customer {
    String name;
    String customerId;
    Account account;

    public Customer(String name, String customerId, Account account) {
        this.name = name;
        this.customerId = customerId;
        this.account = account;
    }
}

class Account {
    String accountNumber;
    double balance;

    public Account(String accountNumber, double balance) {
        this.accountNumber = accountNumber;
        this.balance = balance;
    }

    public void deposit(double amount) {
        balance += amount;
        System.out.println("Deposited " + amount + ". New balance: " + balance);
    }

    public void withdraw(double amount) {
        if (amount <= balance) {
            balance -= amount;
            System.out.println("Withdrew " + amount + ". New balance: " + balance);
        } else {
            System.out.println("Insufficient balance.");
        }
    }
}

class ATM {
    String location;

    public ATM(String location) {
        this.location = location;
    }

    public void processTransaction(Account account, double amount) {
        account.withdraw(amount);
        System.out.println("Processed transaction at " + location);
    }
}
