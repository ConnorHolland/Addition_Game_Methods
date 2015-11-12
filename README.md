# COMSC_1033 Homework #9


## Introduction 
The code below is a revamp of the addition game problem that we have done previously this semester. The addition game was changed from a total of about 200 lines to a mere 50 lines. Creating and calling methods as well as for loops are the programming tricks that made this possible.

## Project Outline
The code is made to ask four questions and award points based off their difficulty. If the previous question was correct the next question will be made harder, if the previous question was incorrect the next question will be made easier.


##  References & Literature
*   Liang, Y. (2014). *Introduction to Java programming: Comprehensive version* (Tenth ed.). 
*   Example from class repository found at: https://github.com/swosu/AdditonGameLoopMethods

## Source Code
```java
package development;
import java.util.*;
public class Sandbox {
public static void main(String[] args) {

		//Call the addition game method
		AdditionGameMethod();
		System.out.println("Thanks for playing :)");
}	
		//Define the addition game method
	public static void AdditionGameMethod() {
		
		int hardness = 100;
		int score = 0;
		
		//Set up my for loop to go through the number of rounds
		int numberOfRounds = 4;
		for(int roundNumber = 1; roundNumber <= numberOfRounds; roundNumber = roundNumber + 1){
			System.out.println("Question " + roundNumber + ":");
			boolean isAnswerCorrect = getAndCheckStudentAnswer(hardness);
			if(isAnswerCorrect){
				System.out.println("Your score is now " + (score = (score + hardness/20)) + ".");
				hardness *= 10;
			}else{
				System.out.println("Your score is now " + score + ".");
				hardness -= 20;
				 }
			}
	}
	
		//Make a method to check answer and display if correct or incorrect
	public static boolean getAndCheckStudentAnswer(int hardness){
		Scanner input = new Scanner(System.in);
		int num1 = (int) ((hardness/100) + Math.random()*hardness/10);
		int num2 = (int) ((hardness/100) + Math.random()*hardness/10);
		System.out.print(num1 + " + " + num2 + " = ");
		int studentAnswer = input.nextInt();
		if(studentAnswer == (num1 + num2)){
			System.out.print("Correct! ");
			return true;
		}else{
			System.out.print("Wrong.... The correct answer was " + (num1 + num2) + ". ");
			return false;
			 }
	
	}
}
```

## Console Output
```
Question 1:
8 + 3 = 1
Wrong.... The correct answer was 11. Your score is now 0.
Question 2:
3 + 7 = 10
Correct! Your score is now 4.
Question 3:
79 + 18 = 
97
Correct! Your score is now 44.
Question 4:
330 + 167 = 497
Correct! Your score is now 444.
Thanks for playing :)
```

## Command Prompt Output
Github was used to make an md file so i could turn my assignment in on canvas. I initiated a repository with an md file and made direct changes on github to the README.md file.


## Summary
I used for loops as well as creating methods for this assignment. The combination of these things allowed me to greatly simplify the addition game we created in homework 6. For loops and methods are very useful as long as you understand the parameters of these two programming tricks.
