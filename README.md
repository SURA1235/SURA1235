import java. util. Scanner;

// ATM Interface
interface ATM {
void checkBalance();
void deposit(double amount);
void withdraw(double amount);
void exit();
}


// SimpleATM Implementation
public class SimpleATM implements ATM {
    private double balance;
    private boolean exit;

    public SimpleATM(double initialBalance) {
        this.balance = initialBalance;
        this.exit = false;
    }

    @Override
    public void checkBalance() {
        System.out.println("Current balance: " + balance);
    }

    @Override
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println(amount + " deposited. Current balance: " + balance);
        } else {
            System.out.println("Invalid deposit amount.");
        }
    }

    @Override
    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            System.out.println(amount + " withdrawn. Current balance: " + balance);
        } else {
            System.out.println("Invalid withdrawal amount or insufficient funds.");
        }
    }

    @Override
    public void exit() {
        exit = true;
        System.out.println("Exiting. Thank you for using the ATM.");
    }

    public boolean isExit() {
        return exit;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        SimpleATM atm = new SimpleATM(1000); // Initial balance of 1000
        int choice;

        while (!atm.isExit()) {
            System.out.println("\nATM Menu:");
            System.out.println("1. Check Balance");
            System.out.println("2. Deposit Money");
            System.out.println("3. Withdraw Money");
            System.out.println("4. Exit");
            System.out.print("Choose an option: ");
            choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    atm.checkBalance();
                    break;
                case 2:
                    System.out.print("Enter deposit amount: ");
                    double depositAmount = scanner.nextDouble();
                    atm.deposit(depositAmount);
                    break;
                case 3:
                    System.out.print("Enter withdrawal amount: ");
                    double withdrawAmount = scanner.nextDouble();
                    atm.withdraw(withdrawAmount);
                    break;
                case 4:
                    atm.exit();
                    break;
                default:
                    System.out.println("Invalid option. Please try again.");
            }
        }

        scanner.close();
    }
}
