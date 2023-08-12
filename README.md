# NumberGame
import java.util.Scanner;
import java.util.Random;

public class NumberGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int round = 3; //Number of rounds user can play
        int attempt = 10; // Number of attempts
        int min = 1; // Minimum value
        int max = 100; // Maximum value
        int match=0;  //score



        for(int j=1;j<=round;j++) {
            System.out.println("Round"+j);

            for (int i = 1; i <= attempt; i++) {
                Random random = new Random();           // Generate a random number between min and max (inclusive)
                int randomNumber = random.nextInt(max - min + 1) + min;

                System.out.print("Enter a number between " + min + " and " + max + ": "); // Enter an integer

                int userInput = scanner.nextInt();


                System.out.println("Attempt:" + i);
                if (userInput == randomNumber) {                        // Compare the user's input with the  random number
                    System.out.println("Congratulations! You guessed the correct number.");
                    System.out.println("You guessed the number on " + i + "th attempt");
                    match++;

                   // break;
                } else {
                    System.out.println("Oops! The correct number was " + randomNumber + ".");
                }
            }
            System.out.println("Your score is : " + match + " in round:" + j);
            System.out.println("Want to play ?");
            System.out.println("1.Yes \n2.No");
            System.out.println("Enter your choice");
            int a ;
             a = scanner.nextInt();
            if(a==2){
                break;
            }

        }
        System.out.println("Thanks for playing");

        scanner.close();
    }
}
