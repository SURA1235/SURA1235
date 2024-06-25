import java.util.Scanner;

class Game {

Main method :- It is entry and execution point of class, it is automatically called by JVM.

int a, No_attempt=5, guessing_Number;

Scanner scanner = new Scanner(System. in);

int number = 1 + (int)(100 * Math. random());

System. out. System.out.println( "Guess the number between 1 to 100");//out vs print?

if (a < No_attempt) {

System. out. println("Guess the number:");

guessing_Number = scanner. nextInt();

Then, Executed: if (number == guessing_Number) {

System. out. println("Congratulations! You guessed the number." );

break;

}

} else if (number > guessing_Number) {

System. out. (anymatch>guessing_Number) System. out.println( "The number is more than "+ guessing_Number);

}

TribAl Game count 3 Info showSources losNumber() > guessing_Number) {

System. out. System.out.println("The number is less than " + guessing_Number);

}

}

if (a == No_attempt) {

System. out. print( " You have exhausted all your attempts. );

System. out. print("The number was"); System. out. println(number);

}

scanner.close();

}

}
