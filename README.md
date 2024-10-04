<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
    <h1>Student Grade System</h1>
    <h2>Overview</h2>
    <p>The <strong>Student Grade System</strong> is a simple Java application that calculates the grade of a student based on the marks obtained in various subjects. The program computes the average percentage and assigns a grade according to a predefined grading scale.</p>
    <h2>Features</h2>
    <ul>
        <li>Input for the number of subjects and their respective marks.</li>
        <li>Calculation of total marks and average percentage.</li>
        <li>Grading system based on average percentage.</li>
        <li>Clear and concise output of results.</li>
    </ul>
    <h3>Grading Scale</h3>
    <table>
        <tr>
            <th>Grade</th>
            <th>Percentage</th>
        </tr>
        <tr>
            <td>A</td>
            <td>&gt;= 90%</td>
        </tr>
        <tr>
            <td>B</td>
            <td>&gt;= 80%</td>
        </tr>
        <tr>
            <td>C</td>
            <td>&gt;= 70%</td>
        </tr>
        <tr>
            <td>D</td>
            <td>&gt;= 60%</td>
        </tr>
        <tr>
            <td>E</td>
            <td>&gt;= 50%</td>
        </tr>
        <tr>
            <td>F</td>
            <td>&lt; 50%</td>
        </tr>
    </table>
    <h2>How to Run</h2>
    <h3>Prerequisites</h3>
    <p>Java Development Kit (JDK) installed on your machine.</p>
    <h3>Compilation and Execution</h3>
    <ol>
        <li><strong>Compile the Java program:</strong>
            <pre><code>javac StudentGradeSystem.java</code></pre>
        </li>
        <li><strong>Run the program:</strong>
            <pre><code>java com.Codesoft.StudentGradeSystem</code></pre>
        </li>
    </ol>
    <h3>Example</h3>
    <pre><code>
Enter the number of subjects: 3
Enter marks for subject 1 (out of 100): 85
Enter marks for subject 2 (out of 100): 92
Enter marks for subject 3 (out of 100): 78

--- Results ---
Total Marks: 255.0
Average Percentage: 85.00%
Grade: B
    </code></pre>
    <h2>Code Explanation</h2>
    <p>The <code>StudentGradeSystem</code> Java program calculates a student's grade based on marks obtained in multiple subjects. Below is a breakdown of the code and its functionality.</p>
    <h3>Package Declaration</h3>
    <pre><code>package com.Codesoft;</code></pre>
    <p>This line declares the package name. In this case, the package is named <code>com.Codesoft</code>. This helps in organizing your code and avoiding naming conflicts.</p>
    <h3>Import Statements</h3>
    <pre><code>import java.util.Scanner;</code></pre>
    <p>This line imports the <code>Scanner</code> class, which is used to read user input from the console.</p>
    <h3>Class Declaration</h3>
    <pre><code>public class StudentGradeSystem {</code></pre>
    <p>This line declares the <code>StudentGradeSystem</code> class, which contains all the methods and the main functionality of the program.</p>
    <h3>Method to Calculate Grade</h3>
    <pre><code>
public static char calculateGrade(double averagePercentage) {
    if (averagePercentage >= 90) {
        return 'A';
    } else if (averagePercentage >= 80) {
        return 'B';
    } else if (averagePercentage >= 70) {
        return 'C';
    } else if (averagePercentage >= 60) {
        return 'D';
    } else if (averagePercentage >= 50) {
        return 'E';
    } else {
        return 'F';
    }
}
    </code></pre>
    <ul>
        <li><strong>Purpose:</strong> This method takes the average percentage as input and returns the corresponding grade as a character (<code>A</code>, <code>B</code>, <code>C</code>, <code>D</code>, <code>E</code>, or <code>F</code>).</li>
        <li><strong>Logic:</strong> It uses a series of <code>if-else</code> statements to determine the grade based on the average percentage.</li>
    </ul>
    <h3>Main Method</h3>
    <pre><code>public static void main(String[] args) {</code></pre>
    <p>The <code>main</code> method is the entry point of the program where the execution begins.</p>
    <h4>Scanner Initialization</h4>
    <pre><code>Scanner scanner = new Scanner(System.in);</code></pre>
    <p>Creates a <code>Scanner</code> object to read input from the user.</p>
    <h4>Input Number of Subjects</h4>
    <pre><code>
System.out.print("Enter the number of subjects: ");
int numSubjects = scanner.nextInt();
    </code></pre>
    <p>Prompts the user to enter the number of subjects and stores it in the <code>numSubjects</code> variable.</p>
    <h4>Marks Input</h4>
    <pre><code>
double[] marks = new double[numSubjects];

for (int i = 0; i < numSubjects; i++) {
    System.out.print("Enter marks for subject " + (i + 1) + " (out of 100): ");
    marks[i] = scanner.nextDouble();
}
    </code></pre>
    <p>An array <code>marks</code> is created to hold the marks for each subject. A <code>for</code> loop iterates over the number of subjects, prompting the user to enter marks for each subject and storing them in the <code>marks</code> array.</p>
    <h4>Total Marks Calculation</h4>
    <pre><code>
double totalMarks = 0;
for (double mark : marks) {
    totalMarks += mark;
}
    </code></pre>
    <p>Initializes <code>totalMarks</code> to zero and uses a <code>for-each</code> loop to calculate the total marks by summing up all the values in the <code>marks</code> array.</p>
    <h4>Average Percentage Calculation</h4>
    <pre><code>double averagePercentage = totalMarks / numSubjects;</code></pre>
    <p>Calculates the average percentage by dividing the total marks by the number of subjects.</p>
    <h4>Grade Determination</h4>
    <pre><code>char grade = calculateGrade(averagePercentage);</code></pre>
    <p>Calls the <code>calculateGrade</code> method with the average percentage to determine the corresponding grade.</p>
    <h4>Output Results</h4>
    <pre><code>
System.out.println("\n--- Results ---");
System.out.println("Total Marks: " + totalMarks);
System.out.printf("Average Percentage: %.2f%%\n", averagePercentage);
System.out.println("Grade: " + grade);
    </code></pre>
    <p>Prints the total marks, average percentage (formatted to two decimal places), and the grade to the console.</p>
    <h4>Scanner Closure</h4>
    <pre><code>scanner.close();</code></pre>
    <p>Closes the <code>Scanner</code> object to free up resources.</p>
    <h3>Summary</h3>
    <p>This program is a simple and effective way to calculate a student's grade based on their performance in multiple subjects. It demonstrates fundamental Java concepts such as classes, methods, arrays, loops, and conditional statements.</p>
    <h2>Author</h2>
    <p>Created by <a href="https://github.com/abhiyyyy7">Abhijeet Behera</a></p>
</body>
</html>
