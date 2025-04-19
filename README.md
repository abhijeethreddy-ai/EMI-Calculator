# EMI-Calculator

import java.util.Scanner;

public class EMICalculator {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input principal, rate and time
        System.out.print("Enter principal amount (P): ");
        double principal = scanner.nextDouble();

        System.out.print("Enter annual interest rate (in %): ");
        double annualRate = scanner.nextDouble();

        System.out.print("Enter loan tenure (in months): ");
        int months = scanner.nextInt();

        scanner.close();

        // Convert annual rate to monthly and percentage to decimal
        double monthlyRate = annualRate / (12 * 100);

        // EMI formula
        double emi = (principal * monthlyRate * Math.pow(1 + monthlyRate, months)) /
                     (Math.pow(1 + monthlyRate, months) - 1);

        System.out.printf("Your EMI is: %.2f\n", emi);
    }
}
