import java.util.Scanner;

public class Calculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        boolean continueCalculation = true;

        System.out.println("Welcome to the Java Calculator!");

        while (continueCalculation) {
            System.out.println("\nSelect an operation:");
            System.out.println("1. Addition (+)");
            System.out.println("2. Subtraction (-)");
            System.out.println("3. Multiplication (*)");
            System.out.println("4. Division (/)");
            System.out.println("5. Modulus (%)");
            System.out.println("6. Exit");

            System.out.print("Enter your choice (1-6): ");
            int choice = scanner.nextInt();

            if (choice == 6) {
                System.out.println("Exiting the Calculator. Thank you!");
                break;
            }

            System.out.print("Enter the first number: ");
            double num1 = scanner.nextDouble();

            System.out.print("Enter the second number: ");
            double num2 = scanner.nextDouble();

            double result = 0;
            boolean validOperation = true;

            switch (choice) {
                case 1:
                    result = num1 + num2;
                    System.out.println("Result: " + num1 + " + " + num2 + " = " + result);
                    break;
                case 2:
                    result = num1 - num2;
                    System.out.println("Result: " + num1 + " - " + num2 + " = " + result);
                    break;
                case 3:
                    result = num1 * num2;
                    System.out.println("Result: " + num1 + " * " + num2 + " = " + result);
                    break;
                case 4:
                    if (num2 != 0) {
                        result = num1 / num2;
                        System.out.println("Result: " + num1 + " / " + num2 + " = " + result);
                    } else {
                        System.out.println("Error: Division by zero is not allowed.");
                        validOperation = false;
                    }
                    break;
                case 5:
                    result = num1 % num2;
                    System.out.println("Result: " + num1 + " % " + num2 + " = " + result);
                    break;
                default:
                    System.out.println("Invalid choice. Please select a valid operation.");
                    validOperation = false;
            }

            if (validOperation) {
                System.out.println("\nWould you like to perform another calculation? (yes/no): ");
                String response = scanner.next();
                if (!response.equalsIgnoreCase("yes")) {
                    continueCalculation = false;
                    System.out.println("Thank you for using the Calculator!");
                }
            }
        }

        scanner.close();
    }
}

