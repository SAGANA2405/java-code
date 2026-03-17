# Mar 3 - String Fundamentals (OneCompiler)

### 1. Length of a string
**Input:** A string  
**Output:** Length of the string

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        int count = 0;
        Scanner sc = new Scanner(System.in);
        String input = sc.nextLine();
        for(int i = 0; i < input.length(); i++) {
            count++;
        }
        System.out.println(count);
    }
}
```

---

### 2. Join the strings
**Input:** Two strings  
**Output:** The two strings joined with a space

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String input = sc.nextLine();
        String input1 = sc.nextLine();
        System.out.println(input + " " + input1);
    }
}
```

---

### 3. Compare the Strings
**Input:** Two strings  
**Output:** Boolean indicating if strings are equal

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String input = sc.nextLine();
        String input1 = sc.nextLine();
        System.out.println(input.equals(input1));
    }
}
```

---

### 4. First character of a string

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String input = sc.nextLine();
        System.out.println(input.charAt(0));
    }
}
```

---

### 5. Last character of a string

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String input = sc.nextLine();
        System.out.println(input.charAt(input.length() - 1));
    }
}
```

---

### 6. Join first & last characters of a string

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String input = sc.nextLine();
        System.out.print(input.charAt(0));
        System.out.println(input.charAt(input.length() - 1));
    }
}
```

---

### 7. Alphanumeric strings check

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String input = sc.nextLine();
        boolean hasLetter = false;
        boolean hasDigit = false;

        for (int i = 0; i < input.length(); i++) {
            char ch = input.charAt(i);
            if (Character.isLetter(ch)) {
                hasLetter = true;
            } else if (Character.isDigit(ch)) {
                hasDigit = true;
            }
            if (hasLetter && hasDigit) {
                break;
            }
        }

        if (hasLetter && hasDigit) {
            System.out.println("true");
        } else {
            System.out.println("false");
        }
    }
}
```

---

### 8. Uppercase check

```java
import java.util.Scanner;

public class UppercaseCheck {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();
        boolean isAllUpper = true;

        for (char ch : input.toCharArray()) {
            if (Character.isLetter(ch) && !Character.isUpperCase(ch)) {
                isAllUpper = false;
                break;
            }
        }
        System.out.println(isAllUpper);
    }
}
```

---

### 9. Lowercase check

```java
import java.util.Scanner;

public class LowercaseCheck {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();
        boolean isAllLower = true;

        for (char ch : input.toCharArray()) {
            if (Character.isLetter(ch) && !Character.isLowerCase(ch)) {
                isAllLower = false;
                break;
            }
        }
        System.out.println(isAllLower);
    }
}
```

---

### 10. String lengths equal or not

```java
import java.util.Scanner;

public class StringLengthCheck {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String str1 = scanner.nextLine();
        String str2 = scanner.nextLine();
        boolean isEqualLength = str1.length() == str2.length();
        System.out.println(isEqualLength);
    }
}
```

---

### 11. Reverse a string

```java
import java.util.Scanner;

public class ReverseString {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();
        String reversed = new StringBuilder(input).reverse().toString();
        System.out.println(reversed);
    }
}
```

---

### 12. Split strings by comma

```java
import java.util.Scanner;

public class SplitByComma {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();
        String[] parts = input.split(",");
        for (String part : parts) {
            System.out.println(part);
        }
    }
}
```

---

### 13. Remove vowels

```java
import java.util.Scanner;

public class RemoveVowels {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();
        String result = input.replaceAll("[aeiouAEIOU]", "");
        System.out.println(result);
    }
}
```

---

### 14. Reverse the character case

```java
import java.util.Scanner;

public class ReverseCase {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();
        StringBuilder result = new StringBuilder();

        for (char ch : input.toCharArray()) {
            if (Character.isUpperCase(ch)) {
                result.append(Character.toLowerCase(ch));
            } else if (Character.isLowerCase(ch)) {
                result.append(Character.toUpperCase(ch));
            } else {
                result.append(ch);
            }
        }
        System.out.println(result.toString());
    }
}
```

---

### 15. Print ascii value

```java
import java.util.Scanner;

public class AsciiValue {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();
        char ch = input.charAt(0);
        System.out.println((int) ch);
    }
}
```

---

### 16. Remove occurrences of a char

```java
import java.util.Scanner;

public class RemoveCharOccurrences {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();
        char toRemove = scanner.nextLine().charAt(0);
        String result = input.replace(String.valueOf(toRemove), "");
        System.out.println(result);
    }
}
```

---

### 17. Search for a word

```java
import java.util.Scanner;

public class SearchWord {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String sentence = scanner.nextLine();
        String word = scanner.nextLine();
        boolean exists = sentence.contains(word);
        System.out.println(exists);
    }
}
```

---

### 18. Count vowels and consonants

```java
import java.util.Scanner;

public class CountVowelsConsonants {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();
        int vowels = 0;
        int consonants = 0;

        for (char ch : input.toLowerCase().toCharArray()) {
            if (ch >= 'a' && ch <= 'z') {
                if ("aeiou".indexOf(ch) != -1) {
                    vowels++;
                } else {
                    consonants++;
                }
            }
        }
        System.out.println(vowels);
        System.out.println(consonants);
    }
}
```

---

### 19. Anagram check

```java
import java.util.Scanner;
import java.util.Arrays;

public class AnagramCheck {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String str1 = scanner.nextLine();
        String str2 = scanner.nextLine();
        str1 = str1.replaceAll("\\s+", "").toLowerCase();
        str2 = str2.replaceAll("\\s+", "").toLowerCase();
        
        if (str1.length() != str2.length()) {
            System.out.println(false);
            return;
        }
        char[] arr1 = str1.toCharArray();
        char[] arr2 = str2.toCharArray();

        Arrays.sort(arr1);
        Arrays.sort(arr2);
        System.out.println(Arrays.equals(arr1, arr2));
    }
}
```

---

### 20. Palindrome check

```java
import java.util.Scanner;

public class PalindromeCheck {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();
        String normalized = input.replaceAll("\\s+", "").toLowerCase();

        boolean isPalindrome = true;
        int n = normalized.length();

        for (int i = 0; i < n / 2; i++) {
            if (normalized.charAt(i) != normalized.charAt(n - 1 - i)) {
                isPalindrome = false;
                break;
            }
        }
        System.out.println(isPalindrome);
    }
}
```
