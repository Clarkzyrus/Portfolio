import java.util.Scanner;
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RhymeChecker {
    public static void main(String[] args) {
      
        Scanner scanner = new Scanner(System.in);
        
        
        System.out.print("Enter the first word: ");
        String word1 = scanner.nextLine();
        
        System.out.print("Enter the second word: ");
        String word2 = scanner.nextLine();
        
        
        String sub = word1.length() >= 2 ? word1.substring(word1.length() - 2) : word1;

        
        String regex = "([a-zA-Z]){1}([a-zA-Z]){" + sub.length() + "}" + " " + "\\b" + sub + "$";
        Pattern pattern = Pattern.compile(regex);

      
        Matcher matcher = pattern.matcher(word2);

        
        if (matcher.find()) {
            System.out.println("The words rhyme!");
        } else {
            System.out.println("The words do not rhyme.");
        }

        
        scanner.close();
    }
}

