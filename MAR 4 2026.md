# Mar 4 - Advanced Strings & Toggles (HackerRank)

### 1. Reverse a string
**Input Format:** First input corresponds to the string.  
**Output Format:** Print the reverse of string.

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        char t = ' ';
        int i;
        char[] strarr1 = str.toCharArray();
        
        int s = 0, e = str.length() - 1;
        while(s < e) {
            t = strarr1[s];
            strarr1[s] = strarr1[e];
            strarr1[e] = t;
            s++;
            e--;
        }
        for(i = 0; i < str.length(); i++) {
            System.out.print(strarr1[i]);
        }
    }
}
```

---

### 2. Execute string statement without blankspace

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        str = str.replaceAll(" ", "");
        System.out.print(str);
    }
}
```

---

### 3. Delete the vowels letter in the string

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        
        str = str.replaceAll("a", "");
        str = str.replaceAll("e", "");
        str = str.replaceAll("i", "");
        str = str.replaceAll("o", "");
        str = str.replaceAll("u", "");
        
        System.out.print(str);
    }
}
```

---

### 4. Concatenation of two strings

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.next();
        String str1 = sc.next();
        System.out.print(str + str1);
    }
}
```

---

### 5. Count the vowel letters in the string

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        char[] strarr = str.toCharArray();
        
        int i, vc = 0, cc = 0;
        for(i = 0; i < str.length(); i++) {
            if(strarr[i] == 'a' || strarr[i] == 'e' || strarr[i] == 'i' || strarr[i] == 'o' || strarr[i] == 'u') 
                vc++;
            else 
                cc++;
        }
        System.out.println(vc);
    }
}
```

---

### 6. Check whether two strings are anagram or not

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str1 = sc.nextLine();
        String str2 = sc.nextLine();
        str1 = str1.toLowerCase().replaceAll(" ", "");
        str2 = str2.toLowerCase().replaceAll(" ", "");
        char[] strarr1 = str1.toCharArray();
        char[] strarr2 = str2.toCharArray();
        
        Arrays.sort(strarr1);
        Arrays.sort(strarr2);
        
        if(Arrays.equals(strarr1, strarr2)) {
            System.out.print("The given strings are an anagram");
        } else {
            System.out.print("The given strings are not an anagram");
        }
    }
}
```

---

### 7. Convert event names to CamelCase

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        
        int n = str.length(), count = 0, i, j;
        char[] arr = str.toCharArray();
        
        arr[0] = (char)(((int)arr[0]) - 32);
        for(i = 1; i < n; i++) {
            if(arr[i] == ' ') {
                for(j = i; j < n - 1; j++) {
                    arr[j] = arr[j+1];
                }
                arr[i] = (char)(((int)arr[i]) - 32);
                count++;
            }
        }

        for(i = 0; i < n - count; i++) {
            System.out.print(arr[i]);
        }
    }
}
```

---

### 8. Toggle each character in a string

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        
        int n = str.length(), i;
        char[] arr = str.toCharArray();
        int c, r;
        
        for(i = 0; i < n; i++) {
            c = (int)arr[i];
            if(arr[i] != ' ') {
                if(c > 96) {
                    r = c - 32;
                    arr[i] = (char)r;
                } else {
                    r = c + 32;
                    arr[i] = (char)r;
                }
            }
        }
        
        for(i = 0; i < n; i++) {
            System.out.print(arr[i]);
        }
    }
}
```

---

### 9. Replace the spaces with a specific character

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        String s = sc.nextLine();
        char c = s.charAt(0);
        int n = str.length(), i;
        char[] arr = str.toCharArray();
        
        for(i = 0; i < n; i++) {
            if(arr[i] == ' ') {
                System.out.print(c);
            } else {
                System.out.print(arr[i]);
            }
        }
    }
}
```

---

### 10. Split strings by space into words

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        int n = str.length(), i;
        char[] arr = str.toCharArray();
        
        for(i = 0; i < n; i++) {
            if(arr[i] == ' ') {
                System.out.println();
            } else {
                System.out.print(arr[i]);
            }
        }
    }
}
```

---

### 11. Count each character in a given string

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        int n = str.length(), count = 1, i, j;
        boolean[] f = new boolean[n];
        
        for(i = 0; i < n; i++) {
            count = 1;
            if(f[i] == false) {
                for(j = i + 1; j < n; j++) {
                    if(str.charAt(i) == str.charAt(j)) {
                        count++;
                        f[j] = true;
                    }
                }
                System.out.println(str.charAt(i) + " " + count);
            }
        }
    }
}
```

---

### 12. Calculate the sum of digits in the given string

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        int n = str.length(), i, sum = 0;
        char c = ' ';
        int cc;
        
        for(i = 0; i < n; i++) {
            c = str.charAt(i);
            if(Character.isDigit(c)) {
               cc = c - '0';
               sum += cc;
            }
        }
        if(sum % 2 == 0) {
            System.out.format("The Sum Of Digit Value is %04d", sum);
        } else {
            System.out.format("The Sum Of Digit Value is %03d", sum);
        }
    }
}
```

---

### 13. Spiral pattern of the string

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        int n = str.length();
        char s = ' ';
        StringBuffer sb = new StringBuffer(str);
        StringBuffer sr = new StringBuffer(str);
        sr.reverse();
        char[][] arr = new char[n][n];
        int i, j;
        
        for(i = 0; i < n; i++) {
            if(i == 0) {
                for(j = 0; j < n; j++) {
                    arr[i][j] = sb.charAt(j);
                }
            }
            if(i == n - 1) {
                for(j = n - 1; j >= 0; j--) {
                    arr[i][j] = sr.charAt(j);
                }
            }
            for(j = 0; j < n; j++) {
                if(j == 0) {
                    arr[i][j] = sb.charAt(i);
                }
                if(j == n - 1) {
                    arr[i][j] = sr.charAt(i);
                }
                if(i != 0 && i != n - 1 && j != 0 && j != n - 1) {
                    arr[i][j] = s;
                }
            }
        }
            
        for(i = 0; i < n; i++) {
            for(j = 0; j < n; j++) {
                System.out.print(arr[i][j]);
            }
            System.out.println();
        }
    }
}
```
