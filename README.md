# Student-tracker-
import java.util.ArrayList;
import java.util.Scanner;
import java.util.Collections;

public class GradeTracker {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        ArrayList<Double> grades = new ArrayList<>();
        
        System.out.println("--- Student Grade Tracker ---");
        System.out.println("Enter student grades (type -1 to finish):");

        while (true) {
            System.out.print("Enter grade: ");
            double grade = scanner.nextDouble();
            
            if (grade == -1) break;
            
            if (grade >= 0 && grade <= 100) {
                grades.add(grade);
            } else {
                System.out.println("Invalid input. Please enter a grade between 0 and 100.");
            }
        }

        if (grades.isEmpty()) {
            System.out.println("No grades were entered.");
        } else {
            displaySummary(grades);
        }
        
        scanner.close();
    }

    public static void displaySummary(ArrayList<Double> grades) {
        double sum = 0;
        double highest = Collections.max(grades);
        double lowest = Collections.min(grades);

        for (double grade : grades) {
            sum += grade;
        }

        double average = sum / grades.size();

        System.out.println("\n--- Summary Report ---");
        System.out.println("Total Students: " + grades.size());
        System.out.printf("Average Score: %.2f\n", average);
        System.out.println("Highest Score: " + highest);
        System.out.println("Lowest Score:  " + lowest);
    }
}
