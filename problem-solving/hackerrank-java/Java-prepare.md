Solutions

Java Stdin and Stdout I

```sql
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int a = scan.nextInt();
        int b = scan.nextInt();
        int c = scan.nextInt();

        System.out.println(a);
        System.out.println(b);
        System.out.println(c);
    }
}
```

Java If-Else

```sql
import java.util.*;

public class Solution {

    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        int N = scanner.nextInt();
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        scanner.close();

        if(N % 2==0) {
            if(N >= 2 && N <= 5) System.out.println("Not Weird");
            else if(N >= 6 && N <= 20) System.out.println("Weird");
            else System.out.println("Not Weird");
        }
        else {
            System.out.println("Weird");
        }
    }
}
```

Java Stdin and Stdout II

```sql
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int i = scan.nextInt();
        double d = scan.nextDouble();
        scan.nextLine();
        String s = scan.nextLine();
        scan.close();

        System.out.println("String: " + s);
        System.out.println("Double: " + d);
        System.out.println("Int: " + i);
    }
}
```

Java Output Formatting

```sql
import java.util.Scanner;

public class Solution {

    public static void main(String[] args) {
            Scanner sc=new Scanner(System.in);
            System.out.println("================================");
            for(int i=0;i<3;i++){
                String s1=sc.next();
                int x=sc.nextInt();
                //Complete this line
                System.out.printf( "%-15s%03d %n", s1, x);
            }
            System.out.println("================================");

    }
}
```

Java Loops I

```sql
import java.util.*;

public class Solution {
    public static void main(String[] args) throws IOException {
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));

        int N = Integer.parseInt(bufferedReader.readLine().trim());

        bufferedReader.close();

        for(int i=1;i<=10;i++){
           System.out.println(N + " x " + i + " = " + N*i);
        }
    }
}
```

Java Loops II

```sql
import java.util.*;
import java.io.*;

class Solution{
    public static void main(String []argh){
        Scanner in = new Scanner(System.in);
        int t=in.nextInt();
        for(int i=0;i<t;i++){
            int a = in.nextInt();
            int b = in.nextInt();
            int n = in.nextInt();

            for(int j = 0; j < n; j++){
                a += b * Math.pow(2, j);
                System.out.print(a + " ");
            }
            System.out.println();
        }
        in.close();
    }
}
```

Java Datatypes

```sql
import java.util.*;
import java.io.*;

class Solution{
    public static void main(String []argh) {
        Scanner sc = new Scanner(System.in);
        int t=sc.nextInt();

        for(int i=0;i<t;i++) {

            try {
                long x=sc.nextLong();
                System.out.println(x+" can be fitted in:");
                if(x>=-128 && x<=127)System.out.println("* byte");
                if(x>=-32768 && x<=32767)System.out.println("* short");
                if(x>=-2147483648 && x<=2147483647)System.out.println("* int");
                if(x>=-Math.pow(2,63) && x<=Math.pow(2,63)-1)System.out.println("* long");

                //Complete the code
            }
            catch(Exception e) {
                System.out.println(sc.next()+" can't be fitted anywhere.");
            }

        }
    }
}
```

Java Int to String

```sql
String s;

   s = String.valueOf(n);
```

Java Date and Time

```sql
import java.util.*;

class Result {

    public static String findDay(int month, int day, int year) {
       return LocalDate.of(year, month, day).getDayOfWeek().name();
    }

}

public class Solution {
    public static void main(String[] args) throws IOException {
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));
        BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(System.getenv("OUTPUT_PATH")));

        String[] firstMultipleInput = bufferedReader.readLine().replaceAll("\\s+$", "").split(" ");

        int month = Integer.parseInt(firstMultipleInput[0]);

        int day = Integer.parseInt(firstMultipleInput[1]);

        int year = Integer.parseInt(firstMultipleInput[2]);

        String res = Result.findDay(month, day, year);

        bufferedWriter.write(res);
        bufferedWriter.newLine();

        bufferedReader.close();
        bufferedWriter.close();
    }
}
```

Java Currency Formatter

```sql
import java.util.*;
import java.text.*;

public class Solution {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        double payment = scanner.nextDouble();
        scanner.close();
         Locale indiaLocale = new Locale("en", "IN");
         NumberFormat us     = NumberFormat.getCurrencyInstance(Locale.US);
         NumberFormat india  = NumberFormat.getCurrencyInstance(indiaLocale);
         NumberFormat china  = NumberFormat.getCurrencyInstance(Locale.CHINA);
         NumberFormat france = NumberFormat.getCurrencyInstance(Locale.FRANCE);

        System.out.println("US: " + us.format(payment));
        System.out.println("India: " + india.format(payment));
        System.out.println("China: " + china.format(payment));
        System.out.println("France: " + france.format(payment));
    }
}
```
