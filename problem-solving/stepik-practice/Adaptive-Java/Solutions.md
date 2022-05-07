1. Problems

1.1 Squirrels and nuts

```sql
import java.util.Scanner;
class Main {
  public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
      int N = sc.nextInt();
      int K = sc.nextInt();
      int S = K / N;
      System.out.println(S);
  }
}
```

1.2 Squirrels and nuts - 2

```sql
import java.util.Scanner;
class Main {
  public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
      int N = sc.nextInt();
      int K = sc.nextInt();
      System.out.println(K % N);
  }
}
```

1.3 Snail

```sql
import java.util.Scanner;
class Main {
  public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
      int H = sc.nextInt();
      int A = sc.nextInt();
      int B = sc.nextInt();
      int t = (1+((H-B)-1)/(A-B));
      System.out.println(t);
  }
}
```

1.4 MKAD

```sql
import java.util.Scanner;
class Main {
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
      int V = sc.nextInt();
      int T = sc.nextInt();
      int S = ((V * T) % 109 + 109) % 109;
      System.out.println(S);
  }
}
```

1.5 Difference of times

```sql
import java.util.Scanner;
class Main {
  public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
      int h1 = sc.nextInt();
      int m1 = sc.nextInt();
      int s1 = sc.nextInt();
      int h2 = sc.nextInt();
      int m2 = sc.nextInt();
      int s2 = sc.nextInt();
      int t = 3600*(h2-h1) + 60*(m2-m1) + (s2-s1);
      System.out.println(t);
  }
}
```

1.6 Digital watches

```sql
import java.util.Scanner;
class Main {
  public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
      int N = sc.nextInt();
      int s = N % 60;
      int m = N / 60 % 60;
      int h = N /3600 % 24;
      System.out.printf("%d" +":"+ "%02d"+":" +"%02d", h,m,s);
  }
}
```

1.7 Desks

```sql
import java.util.Scanner;
class Main {
  public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
      int a = sc.nextInt();
      int b = sc.nextInt();
      int c = sc.nextInt();

      System.out.println( (a + 1) /2 + (b + 1) /2 + (c + 1) /2 );
  }
}
```

1.8 Next even number

```sql
import java.util.Scanner;
class Main {
  public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
      int n = sc.nextInt();
      if(n % 2 == 0) {
          System.out.println(n+2);
      } else {
          System.out.println(n+1);
      }
  }
}
```

1.9 The sum of digits of a three-digit number

```sql
import java.util.Scanner;
class Main {
  public static void main(String[] args) {
       int number, digit, sum = 0;
        Scanner sc = new Scanner(System.in);
        number = sc.nextInt();
        while(number>0) {
            digit = number % 10;

            sum = sum + digit;

            number = number / 10;
        }
        System.out.println(sum);
  }
}
```

1.10 The number of tens

```sql
import java.util.Scanner;
class Main {
  public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
      int N = sc.nextInt();
      N = N/10;
      int n = N % 10;
      System.out.println(n);
  }
}
```

1.11 First digit of the two-digit number

```sql
import java.util.Scanner;
class Main {
  public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
      int n = sc.nextInt();
      System.out.println(n/10);
  }
}
```

1.12 Reversing

```sql
import java.util.Scanner;
class Main {
  public static void main(String[] args) {
      int number, digit, reverse_num = 0;
        Scanner sc = new Scanner(System.in);
        number = sc.nextInt();
        while(number>0) {
            digit = number % 10;

            reverse_num = reverse_num * 10 + digit;

            number = number / 10;
        }
        System.out.println(reverse_num);
  }
}
```

1.18 Triangle

```sql
import java.util.Scanner;

class Main {
  public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);
    int A = sc.nextInt();
    int B = sc.nextInt();
    int C = sc.nextInt();
    if((A+B)>C && (B+C)>A && (A+C)>B) {
        System.out.println("YES");
    } else {
        System.out.println("NO");
    }
  }
}
```

1.21 Floor-space of the room

```sql
import java.util.Scanner;
class Main {
  public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        switch (sc.next()) {
            case "triangle":

                double At = sc.nextDouble(),
                       Bt = sc.nextDouble(),
                       Ct = sc.nextDouble(),
                       p = ((At+Bt+Ct)/2),
                       S = Math.sqrt(p*(p-At)*(p-Bt)*(p-Ct));

                System.out.println(S);
                break;

            case "rectangle":

                double Ar = sc.nextDouble(),
                Br = sc.nextDouble();

                System.out.println(Ar * Br);

                break;

            case "circle":

                double Range = sc.nextDouble();
                System.out.println(3.14 * Range * Range);

                break;

            default:
                break;
        }
  }
}
```

1.23 Direction

```sql
import java.util.Scanner;
class Main {
  public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
        try {
            int N = sc.nextInt();
            switch (N) {
                case 0:
                    System.out.println("do not move");
                    break;
                case 1:
                    System.out.println("move up");
                    break;
                case 2:
                    System.out.println("move down");
                    break;
                case 3:
                    System.out.println("move left");
                    break;
                case 4:
                    System.out.println("move right");
                    break;
                default:
                    System.out.println("error!");
            }
        } catch (Exception e) {
            System.out.println("error!");
        }
  }
}
```

1.28 Fractional part

```sql
import java.util.Scanner;
class Main {
  public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
      double X = sc.nextDouble();
      double x = X - (int)X;
      System.out.printf("%f %n", x);
  }
}
```

1.29 Fractional part 2

```sql
import java.util.Scanner;
class Main {
  public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
      double d = sc.nextDouble();
      int n = (int)(d*10)%10;
      System.out.println(n);
  }
}
```

1.30 Deposit

```sql
import java.util.Scanner;

class Main {
  public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
      int P = sc.nextInt();
      int X = sc.nextInt();
      int Y = sc.nextInt();

      int z = ((100+P)*(100*X+Y))/100;
      int n = z % 100;
      int m = (z-n)/100;
      System.out.println(m);
      System.out.println(n);
  }
}
```

1.38 Grades

```sql
import java.util.Scanner;

class Main {
  public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
        int N = sc.nextInt();

        int A=0, B=0, C=0, D=0;
        for(int i=0; i<N; i++) {
            int n = sc.nextInt();
            if(n==2) {
                D++;
            } else if(n==3) {
                C++;
            } else if(n==4) {
                B++;
            } else {
                A++;
            }
        }
        System.out.println(D+" " +C+" "+B+" "+A);
  }
}
```

1.58 Palindrome

```sql
import java.util.Scanner;

class Main {
  public static void main(String[] args) {
      Scanner sc = new Scanner(System.in);
      String str = sc.next();
      String rev = "";
        int length = str.length();

        for(int i=length-1; i>=0; i--) {
            rev = rev + str.charAt(i);
        }

        if(str.equals(rev)) {
            System.out.println("yes");
        } else {
            System.out.println("no");
        }
  }
}
```

1.62 Anagrams

```sql
import java.util.Arrays;
import java.util.Scanner;

class Main {
  static String IsAnagram(String str1, String str2){
        if(str1.length() != str2.length()){
            return  "False";
        }

        char[] arr1 = str1.toCharArray();
        char[] arr2 = str2.toCharArray();
        Arrays.sort(arr1);
        Arrays.sort(arr2);
        if(!Arrays.equals(arr1, arr2)){
            return "False";
        }
        return "True";
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String s1 = sc.nextLine().toLowerCase();
        String s2 = sc.nextLine().toLowerCase();
        System.out.println(IsAnagram(s1, s2));
    }
}
```
