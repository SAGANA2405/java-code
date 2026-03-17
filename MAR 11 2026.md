# Mar 11 - Frequencies & Array Replacements (HackerRank)

### 1. Check whether the string is isogram or not

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String s = sc.nextLine();
        int frq[] = new int[26];
        for(int i = 0; i < s.length(); i++){
            if(s.charAt(i) != ' ')
                frq[s.charAt(i) - 97]++;
        }
        for(int i = 0; i < 26; i++){
            if(frq[i] > 1){
                System.out.print("NOT ISOGRAM");
                return;
            }
        }
        System.out.print("ISOGRAM");
    }
}
```

---

### 2. Check the given string is anagram or not

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String s1 = sc.next();
        String s2 = sc.next();
        String s3 = s1;
        String s4 = s2;
        s1 = s1.toLowerCase();
        s2 = s2.toLowerCase();
        int frq1[] = new int[26];
        int frq2[] = new int[26];
        
        for(int i = 0; i < s1.length(); i++){
            frq1[s1.charAt(i) - 'a']++;
        }
        for(int i = 0; i < s2.length(); i++){
            frq2[s2.charAt(i) - 'a']++;
        }
        for(int i = 0; i < 26; i++){
            if(frq1[i] != frq2[i]){
                System.out.print(s3 + " and " + s4 + " are Not Anagrams.");
                return;
            }
        }
        System.out.print(s3 + " and " + s4 + " are Anagrams.");
    }
}
```

---

### 3. Check whether a given string is Pangram or not

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String s = sc.nextLine();
        s = s.toLowerCase();
        int freq[] = new int[26];
        
        for(int i = 0; i < s.length(); i++){
            if(Character.isLetter(s.charAt(i))){ 
                freq[s.charAt(i) - 'a']++;
            }
        }
        for(int i = 0; i < 26; i++){
            if(freq[i] < 1){
                System.out.print("Not Pangrams");
                return;
            }
        }
        System.out.print("Pangrams");
    }
}
```

---

### 4. Count each character in the string

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String s = sc.nextLine();
        s = s.toLowerCase();
        int freq[] = new int[26];
        
        for(int i = 0; i < s.length(); i++){
            if(Character.isLetter(s.charAt(i))){ 
                freq[s.charAt(i) - 'a']++;
            }
        }
        for(int i = 0; i < s.length(); i++){
            if(freq[s.charAt(i) - 97] != 0){ 
                System.out.println(s.charAt(i) + " " + freq[s.charAt(i) - 97]);
                freq[s.charAt(i) - 97] = 0;                                         
            }
        }
    }
}
```

---

### 5. Replace element with greatest on right side

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int arr[] = new int[n];

        for(int i = 0; i < n; i++){
            arr[i] = sc.nextInt();
        }

        int maxRight = -1;
        for(int i = n - 1; i >= 0; i--){
            int temp = arr[i];
            arr[i] = maxRight;

            if(temp > maxRight){
                maxRight = temp;
            }
        }

        for(int i = 0; i < n; i++){
            System.out.print(arr[i] + " ");
        }
    }
}
```

---

### 6. Remove Single Vowel (and retain consecutive vowels)

```java
import java.util.*;

public class Main {
    public static boolean isVowel(char c) {
        c = Character.toLowerCase(c);
        return c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u';
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String s = sc.nextLine();
        StringBuilder result = new StringBuilder();

        int i = 0;
        while (i < s.length()) {
            if (isVowel(s.charAt(i))) {
                int j = i;
                while (j < s.length() && isVowel(s.charAt(j))) {
                    j++;
                }
                int count = j - i;
                if (count >= 2) {
                    result.append(s.substring(i, j));
                }
                i = j;
            } 
            else {
                result.append(s.charAt(i));
                i++;
            }
        }
        System.out.println(result.toString());
    }
}
```
