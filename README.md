Capitalize the First and Last letter
Today we will look at java program, we’re going to capitalize all the first and last character of the words in a string.

Lets understand with the help of an example.
Input String:- prepinsta
Output String:- PrepinstA

Capitalize The First and Last Letter in java
Algorithm
Take a string input from the user and store it in the variable called “s”.
Take a “newstr” variable initialize with an empty string.
Split the string into words and store it in the String array using regex.
Take a for-each loop and store the first character by using subString() and store it in the “firstchar” and rest of the string store in “restchar” .
Then add the “firstchar” and “restchar” string in “newstr”.
Note
Take a string input from the user and store it in the variable called "s". Take a new variable "newstr" and initialize it with an empty string. Split the string into words and store it in the String array using regex. Take a for-each loop and store the first character by using subString() and capitalize that first character using upperCase() method and store it in the "firstchar" and rest of the string from 1 to length-1 store in "restchar" , get the last character of string using charAt() method and convert that character to string using toString() and then add the "firstchar" and "restchar" string in "newstr"
Code in Java
import java.util.Scanner;
public class CapitalizeTheFirstAndLastLetterOfString {
   public static void main(String[] args) {
     Scanner sc =new Scanner(System.in);
     System.out.print("Enter String : "); 
     String s = sc.nextLine();
     String newstr = "";

     String[] str = s.split("\\s"); // splitting sentence into word converted to String array

    for (String string : str) {     
      int length = string.length();
      String firstchar = string.substring(0, 1);
      String restchar = string.substring(1, length - 1);
      String lastchar = Character.toString(string.charAt(length - 1));
      newstr = newstr+firstchar.toUpperCase()+restchar+" ";
    } 
    System.out.println(newstr); 
  }
}
Output
Enter String : prep inst is best
PreP InstA IS BesT 
Method 2 (Capitalize the First and Last letter)
class Main {
    static String FirstAndLast(String str)
    {
        // Create an equivalent char array of given string
        char[] ch = str.toCharArray();
        for (int i = 0; i < ch.length; i++) {

            // k stores index of first character and i is going to store index of last character.
            int k = i;
            while (i < ch.length && ch[i] != ' ')
                i++;

            // Check if the character is a small letter If yes, then Capitalise
            ch[k] = (char)(ch[k] >= 'a' && ch[k] <= 'z'
                               ? ((int)ch[k] - 32)
                               : (int)ch[k]);
            ch[i - 1] = (char)(ch[i - 1] >= 'a' && ch[i - 1] <= 'z'
                                   ? ((int)ch[i - 1] - 32)
                                   : (int)ch[i - 1]);
        }
        return new String(ch);
    }

    public static void main(String args[])
    {
        String str = "Prep insta";
        System.out.println("Input String:- "+str);
        System.out.println("String after Capitalize the first and last character of each word in a string:- "+FirstAndLast(str));
    }
}
Output
Input String:- Prep insta
String after Capitalize the first and last character of each word in a string:- PreP InstA
