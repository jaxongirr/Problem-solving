Day 0: Hello, World

```sql
import java.util.*;
public class Solution {
   public static void main(String[] args) {

      Scanner scan = new Scanner(System.in)
      String inputString = scan.nextLine();
      scan.close();

      System.out.println("Hello, World.");
      System.out.println(inputString);
   }
}
```

Day 1: Data Types

```sql
public class Solution {
   public static void main(String[] args) {
        int i = 4;
        double d = 4.0;
        String s = "HackerRank ";

        Scanner scan = new Scanner(System.in);
        int i2;
        double d2;
        String s2;

        i2 = scan.nextInt();
        d2 = scan.nextDouble();
        scan.nextLine();
        s2 = scan.nextLine();

        System.out.println(i + i2);

        System.out.println(d + d2);

        System.out.println(s + s2);

        scan.close();
   }
}
```

Day 2: Operators

```sql
import java.text.*;
import java.util.*;
import static java.util.stream.Collectors.joining;
import static java.util.stream.Collectors.toList;

class Result {

    public static void solve(double meal_cost, int tip_percent, int tax_percent) {
       double tip = meal_cost * tip_percent / 100;
       double tax = tax_percent * meal_cost / 100;
       System.out.println(Math.round(meal_cost + tip + tax));
    }
}

public class Solution {
    public static void main(String[] args) throws IOException {
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));

        double meal_cost = Double.parseDouble(bufferedReader.readLine().trim());

        int tip_percent = Integer.parseInt(bufferedReader.readLine().trim());

        int tax_percent = Integer.parseInt(bufferedReader.readLine().trim());

        Result.solve(meal_cost, tip_percent, tax_percent);

        bufferedReader.close();
    }
}
```

Day 3: Intro to Conditional Statements

```sql
public class Solution {
    public static void main(String[] args) throws IOException {
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));

        int N = Integer.parseInt(bufferedReader.readLine().trim());

        bufferedReader.close();

        if(N % 2 == 0){
            if(N>=2 && N<=5)
            System.out.println("Not Weird");
            else if(N>=6 && N<=20)
            System.out.println("Weird");
            else
            System.out.println("Not Weird");
        }
        else
        System.out.println("Weird");

    }
}

```

Day 4: Class vs. Instance

```sql
public class Person {
    private int age;

	public Person(int initialAge) {
          if(initialAge < 0){
              age = 0;
              System.out.println("Age is not valid, setting age to 0.");
          }
          else {
              age = initialAge;
          }

	}

	public void amIOld() {
          if(age < 13) {
              System.out.println("You are young.");
          }
          else if(age >= 13 && age < 18) {
              System.out.println("You are a teenager.");
          }
          else {
              System.out.println("You are old.");
          }
	}

	public void yearPasses() {
          age += 1;
	}
```

Day 5: Loops

```sql
public class Solution {
    public static void main(String[] args) throws IOException {
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));

        int n = Integer.parseInt(bufferedReader.readLine().trim());

        bufferedReader.close();
        for(int i=1;i<=10;i++){
            System.out.println(n + " x " + i + " = " +n*i);
        }
    }
}
```

Day 6: Let's Review

```sql
import java.io.*;
import java.util.*;

public class Solution {
   public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);

        int T = scan.nextInt();
        for (int i = 0; i < T; i++) {
            String str = scan.next();
            char[] arrayChar = str.toCharArray();
            for (int j = 0; j < arrayChar.length; j += 2) {
                System.out.print(arrayChar[j]);
            }
           System.out.print(" ");
            for (int l = 1; l < arrayChar.length; l+=2) {
                System.out.print(arrayChar[l]);
            }
            System.out.println();
        }
    }
}
```

Day 7: Arrays

```sql
import java.util.*;

public class Solution {
    public static void main(String[] args)  {
        Scanner scan = new Scanner(System.in);
        int N = scan.nextInt();
        int[] arr = new int[N];
         for(int i=0; i<N; i++){
             arr[i] = scan.nextInt();
         }
         scan.close();
         for(int i=0;i<N;i++){
             System.out.print(arr[N- 1 - i] + " ");
         }
    }
}
```

Day 8: Dictionaries and Maps

```sql
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int n = in.nextInt();
        Map<String,Integer> myMap = new HashMap<String,Integer>();
        for (int i = 0; i < n; i++) {
            String name = in.next();
            int phone = in.nextInt();
            in.nextLine();
            myMap.put(name, phone);
        }
        while (in.hasNext()) {
            String s = in.next();
            if (myMap.get(s) == null)
                System.out.println("Not found");
            else {
                System.out.println(s + "=" + myMap.get(s));
            }
        }
        in.close();
    }
}

```

Day 9: Recursion 3

```sql
import java.util.*;

class Result {
    public static int factorial(int n) {
     if(n <= 1) { return 1;}
     else {
         return n * factorial(n - 1);
     }
    }

}

public class Solution {
    public static void main(String[] args)  {
        Scanner scan = new Scanner(System.in);
        int n = scan.nextInt();

        int result = Result.factorial(n);
        System.out.println(result);
    }
}
```

Day 10: Binary Numbers

```sql
import java.util.*;

public class Solution {
    public static void main(String[] args)  {
        Scanner scan = new Scanner(System.in);
        int n = scan.nextInt();
        int rem = 0, s = 0, t =0;
        while(n > 0){
            rem = n % 2;
            n = n/2;
            if(rem == 1) {
                s++;
                if(s > t) { t = s;}
            }
            else {
                s = 0;
            }
        }
        System.out.println(t);
    }
}
```

Day 11: 2D Arrays

```sql
import java.util.*;

public class Solution {
    public static void main(String[] args)  {
        Scanner scan = new Scanner(System.in);
        int[][] arr = new int[6][6];
        for(int i = 0; i < 6; i++){
            for(int j = 0; j<6; j++){
                arr[i][j]= scan.nextInt();
            }
        }
        int max = -63;
        for(int i = 0; i< 6; i++){
            for(int j = 0; j < 6; j++){
                if(j + 2 < 6 && i + 2 < 6){
                    int sum = arr[i][j] + arr[i][j+1] + arr[i][j+2] + arr[i+1][j+1] + arr[i+2][j] + arr[i+2][j+1] + arr[i+2][j+2];
                    if(sum > max) { max = sum;}
                }
            }
        }
        System.out.println(max);
    }
}
```

Day 12: Inheritance

```sql
class Student extends Person{
	private int[] testScores;

    public Student(String firstName, String lastName, int id, int[] scores ){
        super(firstName, lastName, id);
        this.testScores = scores;
    }

    public char calculate(){
        int sum = 0;
        int avg = 0;
        char grade = ' ';
        for(int n : testScores){
            sum += n;
        }
        if(sum > 0) {
            avg = (int)Math.ceil(sum/testScores.length);
        }
        if(avg >= 90 && avg <= 100) grade = 'O';
        else if(avg >=80 && avg < 90) grade = 'E';
        else if(avg >=70 && avg < 80) grade = 'A';
        else if(avg >=55 && avg < 70) grade = 'P';
        else if(avg >=40 && avg < 55) grade = 'D';
        else grade = 'T';
        return grade;
    }
}
```

Day 13: Abstract Classes

```sql
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String title = sc.nextLine();
        String author = sc.nextLine();
        int price = sc.nextInt();
        sc.close();

        System.out.println("Title: " + title);
        System.out.println("Author: " + author);
        System.out.println("Price: " + price);

    }
}
```

Day 14: Scope

```sql
public Difference(int [] Elements){
        this.elements = Elements;
}

    public void computeDifference() {
        Arrays.sort(elements);
        maximumDifference = elements[elements.length-1] - elements[0];
    }
```

Day 16: Exceptions - String to Integer

```sql
import java.util.*;

public class Solution {
    public static void main(String[] args) {
         Scanner scan = new Scanner(System.in);
        String s = scan.next();
        try{
            System.out.println(Integer.parseInt(s));
        }
        catch(Exception e){
            System.out.println("Bad String");
        }
    }
}
```

Day 19: Interfaces

```sql
import java.util.Scanner;

public class Test {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        Calculator calculator = new Calculator(sc.nextInt());
        calculator.divisorSum();
    }
}

interface AdvancedArithmetic {

    void divisorSum();
}

class Calculator implements AdvancedArithmetic {

    private int n;
    int sum = 0;

    public Calculator(int n) {
        this.n = n;
    }

    @Override
    public void divisorSum() {
        System.out.println("I implemented: AdvancedArithmetic");
        for(int i=1; i<=n; i++) {
            if(n % i == 0) {
                sum += i;
            }
        }
        System.out.println(sum);
    }
}
```

Day 20: Sorting

```sql
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] a = new int[n];
        for(int i=0; i<n; i++) {
            a[i] = sc.nextInt();
        }

        int totalSwaps = 0;
        for(int i=0; i<n; i++) {
            int numberOfSwaps = 0;

            for(int j=0; j<n-1; j++) {
                if(a[j] > a[j+1]) {
                    int temp = a[j+1];
                    a[j+1] = a[j];
                    a[j] = temp;
                    numberOfSwaps++;
                    totalSwaps++;
                }
            }
            if(numberOfSwaps == 0) {
                break;
            }
        }
        System.out.println("Array is sorted in "+totalSwaps+" swaps.");
        System.out.println("First Element: "+a[0]);
        System.out.println("Last Element: "+a[n-1]);
    }
}
```
