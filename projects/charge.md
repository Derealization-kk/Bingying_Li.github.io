---
layout: project
type: project
image: img/charge/0eb0a00b2e74d147a65de47fc3b66a2.jpg
title: Correct Charge
date: 2022
published: true
labels:
  - Java
summary: "ICS 111 Homework "
---
<img class="img-fluid" src="../img/charge/f50b9e4c8031a87f2ec51afe2f2df07.png">
<hr>
This project is a simple change calculator program called "CorrectChange". It is designed to help users calculate the change amount after purchasing an item to ensure the correct transaction amount. The user needs to enter the price of the item and the payment amount, and then the program will calculate the change amount and split it in dollars, quarters, 10 cents, 5 cents, and 1 cent coins/notes to display the change amount. Zero details.
<br>
My role and work:
I am the developer of this project, responsible for designing and writing this program.
<br>
I designed the program's user interface, including a message prompting the user to enter the price of the item and the payment amount, as well as a section that displays the change amount. I wrote the core logic of the program, including accepting user input, calculating the change amount, and breaking the change amount into coin units of different denominations. Checks and handling of incorrect or unreasonable values entered by the user have also been added to ensure that the program can give appropriate feedback when the user enters an incorrect value.
<pre>
  public class CorrectChange {

  /**
   *  change money.
   *  
   * @param args - comment line. Not use.
   */
  public static void main(String[] args) {
    Scanner input = new Scanner(System.in);
    //ask user cost
    System.out.println("How much does the item cost?");
    double cost = input.nextDouble();
    //ask user paid
    System.out.println("How much was paid?");
    double paid = input.nextDouble();
    if (paid >= cost) {
      // the change
      double change = Math.round((paid - cost) * 100);
      // number of dollar
      final int changeDollar = (int)(change / 100);
      change = change % 100;
      //change = change - changeDollar * 100;
      // number of quarter
      final int changeQuarter = (int)(change / 25);
      // remaining change
      change = change % 25;
      // number of dimes
      int changeDimes = (int)(change / 10);
      //remaining change
      change = change % 10;
      // number of nickels
      int changeNickels = (int)(change / 5);
      //remaining change
      change = change % 5;
      // number of pennies
      int changePennies = (int)(change / 1);
      System.out.println("The change is " 
          + changeDollar 
          + " dollars, " + changeQuarter + " quarters, " 
          + changeDimes + " dimes," 
          + changeNickels + " nickels, and " + changePennies + " pennies.");
    } else {
      System.out.println("You don't have enough money to pay");
      // the change
      int change = (int)((paid - cost) * 100);
      // number of dollar
      int dollar = change / 100;
      change = change - dollar * 100;
      // number of quarter
      final int quarter = change / 25 * -1;
      // remaining change
      change = change % 25;
      // number of dimes
      final int dimes =  change / 10 * -1;
      //remaining change
      change = change % 10;
      // number of nickels
      final int nickels = change / 5 * -1;
      //remaining change
      change = change % 5;
      // number of pennies
      final int pennies = change / 1 * -1;
      dollar *= -1;
      
      System.out.println("You still need to pay " 
          + dollar 
          + " dollars, " + quarter + " quarters, " 
          + dimes + " dimes," 
          + nickels + " nickels, and " + pennies + " pennies.");
    }
    input.close();
    
    
  }

}
</pre>
