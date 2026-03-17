# Mar 2 - String Manipulations

### 1. Compare Strings
**Input Format:** Accept two strings as input  
**Output Format:** Equal / Not Equal

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String Str1 = sc.next();
        String Str2 = sc.next();
        if(Str1.equals(Str2)){
            System.out.print("Equal");
        }
        else{
            System.out.print("Not Equal");
        }
    }
}
```

---

### 2. Search for a character in a string
**Input Format:** Accept character and string as input  
**Output Format:** Present / Not Present

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String Str1 = sc.nextLine();
        String Str2 = sc.nextLine();
        if(Str2.contains(Str1)){
            System.out.print("Present");
        }
        else{
            System.out.print("Not Present");
        }
    }
}
```

---

### 3. Replace all vowels with spaces

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String Str1 = sc.nextLine();
        String Str2 = Str1.replaceAll("[AEIOUaeiou]", " ");
        System.out.print(Str2);
    }
}
```

---

### 4. Count the special characters in the given string

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String Str1 = sc.nextLine();
        int count = 0;
        for (int i = 0; i < Str1.length(); i++){
            if(!Character.isLetterOrDigit(Str1.charAt(i))){
                count++;
            }
        }
        System.out.print(count);
    }
}
```

---

### 5. Check if the given string is Anagram or not

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String s1 = sc.nextLine();
        String s2 = sc.nextLine();

        String a = s1.toLowerCase();
        String b = s2.toLowerCase();

        if(a.length() != b.length()) {
            System.out.println(s1 + " and " + s2 + " are Not Anagrams.");
            return;
        }

        int count[] = new int[26];
        for(int i = 0; i < a.length(); i++) {
            count[a.charAt(i) - 'a']++;
            count[b.charAt(i) - 'a']--;
        }

        boolean flag = true;
        for(int i = 0; i < 26; i++) {
            if(count[i] != 0) {
                flag = false;
                break;
            }
        }

        if(flag)
            System.out.println(s1 + " and " + s2 + " are Anagrams.");
        else
            System.out.println(s1 + " and " + s2 + " are Not Anagrams.");
    }
}
```

---

### 6. Check whether the string is an Isogram or not
*(An Isogram is a string with no repeating characters)*

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String s = sc.nextLine().toLowerCase();
        boolean isogram = true;

        for(int i = 0; i < s.length(); i++) {
            if(s.charAt(i) == ' ')
                continue;

            for(int j = i + 1; j < s.length(); j++) {
                if(s.charAt(i) == s.charAt(j)) {
                    isogram = false;
                    break;
                }
            }
            if(!isogram)
                break;
        }

        if(isogram)
            System.out.println("ISOGRAM");
        else
            System.out.println("NOT ISOGRAM");
    }
}
```

---

### 7. TCS NQT: '*' and '#' Minimum required count
**Problem:** Find the difference between '*' and '#' in the string.

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String s = sc.nextLine();

        int star = 0;
        int hash = 0;

        for(int i = 0; i < s.length(); i++) {
            if(s.charAt(i) == '*')
                star++;
            else if(s.charAt(i) == '#')
                hash++;
        }

        System.out.println(star - hash);
    }
}
```
