# ATM
package OASIS;

import java.util.Scanner;

    public class ATM {
        private static double balance = 1000; // Initial balance

        public static void main(String[] args) {
            Scanner scanner = new Scanner(System.in);
            int choice;

            do {
                System.out.println("ATM MENU:");
                System.out.println("1. Check Balance");
                System.out.println("2. Withdraw Money");
                System.out.println("3. Deposit Money");
                System.out.println("4. Exit");
                System.out.print("Enter your choice: ");
                choice = scanner.nextInt();

                switch (choice) {
                    case 1:
                        checkBalance();
                        break;
                    case 2:
                        withdrawMoney();
                        break;
                    case 3:
                        depositMoney();
                        break;
                    case 4:
                        System.out.println("Thank you for using the ATM!");
                        break;
                    default:
                        System.out.println("Invalid choice. Please try again.");
                }
            } while (choice != 4);

            scanner.close();
        }

        private static void checkBalance() {
            System.out.println("Current Balance: $" + balance);
        }

        private static void withdrawMoney() {
            Scanner scanner = new Scanner(System.in);
            System.out.print("Enter the amount to withdraw: ");
            double amount = scanner.nextDouble();

            if (amount > balance) {
                System.out.println("Insufficient funds. Please try again.");
            } else {
                balance -= amount;
                System.out.println("Withdrawal successful. Remaining balance: $" + balance);
            }
        }

        private static void depositMoney() {
            Scanner scanner = new Scanner(System.in);
            System.out.print("Enter the amount to deposit: ");
            double amount = scanner.nextDouble();

            if (amount <= 0) {
                System.out.println("Invalid amount. Please try again.");
            } else {
                balance += amount;
                System.out.println("Deposit successful. Current balance: $" + balance);
            }
        }
    }


