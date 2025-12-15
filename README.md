# StudentGradeCalculator-
Java program to calculate student grades
import java.util.Scanner;

/*
 * Student Grade Calculator
 * This program calculates a student's average score
 * and determines the corresponding letter grade.
 */
public class StudentGradeCalculator {

    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);

        // Ask for student name
        System.out.print("Enter student name: ");
        String studentName = input.nextLine();

        // Ask how many scores will be entered
        System.out.print("Enter number of scores: ");
        int numberOfScores = input.nextInt();

        double total = 0;

        // Loop to collect scores
        for (int i = 1; i <= numberOfScores; i++) {
            double score;

            // Validate score input
            while (true) {
                System.out.print("Enter score " + i + ": ");
                score = input.nextDouble();

                if (score >= 0 && score <= 100) {
                    break;
                } else {
                    System.out.println("Invalid score. Enter a value between 0 and 100.");
                }
            }

            total += score;
        }

        // Calculate average
        double average = total / numberOfScores;
        char letterGrade;

        // Determine letter grade
        if (average >= 90) {
            letterGrade = 'A';
        } else if (average >= 80) {
            letterGrade = 'B';
        } else if (average >= 70) {
            letterGrade = 'C';
        } else if (average >= 60) {
            letterGrade = 'D';
        } else {
            letterGrade = 'F';
        }

        // Display results
        System.out.println("\nStudent Name: " + studentName);
        System.out.println("Average Score: " + average);
        System.out.println("Final Grade: " + letterGrade);

        input.close();
    }
}
