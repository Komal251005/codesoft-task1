import java.util.Random;
import java.util.Scanner;

public class NumberGame {
    public static void main(String[] args) {
		System.out.println("                                Welcome to the Number Guessing Game!");
		System.out.println("_________________________________________________________________________________________________-");
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        boolean playAgain = true;
        while (playAgain) {
            int targetNumber = random.nextInt(100) + 1;
            int attempts = 1;
            int maxAttempts = 10;
            System.out.println("I have selected a number between 1 to 100. Guess the number in 10 attempts");
            while (attempts <= maxAttempts) {
                System.out.print("Enter your guess: ");
                int userGuess = scanner.nextInt();
                scanner.nextLine();
                attempts++;
                if (userGuess == targetNumber) {
					System.out.println("------------------------------------------------------------------");
                    System.out.println("Congratulations! You guessed the number " );
                    System.out.println("Target number was:"+targetNumber);
					System.out.println("Your Attempts:"+ attempts );
					if (attempts==1)
					{
						System.out.println("Score:100%");
					}
					else if (attempts==2)
					{
						System.out.println("score:90%");
					}
					else if (attempts==3)
					{
						System.out.println("score:80%");
					}
					else if (attempts==4)
					{
						System.out.println("score:70%");
					}
					else if (attempts==5)
					{
						System.out.println("score:60%");
					}
					else if (attempts==6)
					{
						System.out.println("score:50%");
					}
					else if (attempts==7)
					{
						System.out.println("score:40%");
					}
					else if (attempts==8)
					{
						System.out.println("score:30%");
					}
					else if (attempts==9)
					{
						System.out.println("score:20%");
					}
					else{
						System.out.println("score:10%");
					}
                    break;
                } else if (userGuess < targetNumber) {
                    System.out.println("Too low! Try again.");
                } else {
                    System.out.println("Too high! Try again.");
                }
            }
            if (attempts > maxAttempts) {
                System.out.println("Sorry, you've run out of attempts. The correct number was " + targetNumber + ".");
				System.out.println("Score:0");
            }
            System.out.print("Do you want to play again? (yes/no): ");
			     String playAgainInput = scanner.nextLine();
            playAgain = playAgainInput.equalsIgnoreCase("yes");
        }
        scanner.close();
}
}

