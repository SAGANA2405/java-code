# Mar 10 - Strings & Binary Search (HackerRank & LeetCode)

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
            if(s.charAt(i) != ' '){
                frq[s.charAt(i) - 97]++;
            }
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
        String str1 = sc.nextLine();
        String s = str1.toLowerCase();
        String str2 = sc.nextLine();
        String st = str2.toLowerCase();
        int frq[] = new int[26];
        
        for(int i = 0; i < s.length(); i++){
            frq[s.charAt(i) - 97]++;
        }
        for(int i = 0; i < st.length(); i++){
            frq[st.charAt(i) - 97]--;
        }
        for(int i = 0; i < 26; i++){
            if(frq[i] != 0){
                System.out.print(str1 + " and " + str2 + " are Not Anagrams.");
                return;
            }
        }
        System.out.print(str1 + " and " + str2 + " are Anagrams.");
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
        int frq[] = new int[26];
        
        for(int i = 0; i < s.length(); i++){
            if(s.charAt(i) >= 'a' && s.charAt(i) <= 'z' ){
                frq[s.charAt(i) - 97]++;
            }
        }
        for(int i = 0; i < 26; i++){
            if(frq[i] == 0){
                System.out.print("Not Pangrams");
                return;
            }
        }
        System.out.print("Pangrams");
    }
}
```

---

### 4. Count each character in a given string

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String s = sc.nextLine();
        int frq[] = new int[26];
        
        for(int i = 0; i < s.length(); i++){
            if(s.charAt(i) != ' '){
                frq[s.charAt(i) - 97]++;
            }
        }
        for(int i = 0; i < s.length(); i++){
            char c = s.charAt(i);
            int n = frq[c - 97];
            if(frq[c - 97] != 0){
                System.out.println(c + " " + n);
            }
            frq[c - 97] = 0;
        }
    }
}
```

---

### 5. Binary Search (LeetCode 704)

```java
class Solution {
    public int search(int[] arr, int target) {
        int start = 0, end = arr.length - 1, mid;
        while(start <= end){
            mid = (start + end) / 2;
            if(arr[mid] == target) return mid;
            if(arr[mid] > target) end = mid - 1;
            else start = mid + 1;
        }
        return -1; 
    }
}
```

---

### 6. Reverse String (LeetCode 344)

```java
class Solution {
    public void reverseString(char[] s) {
        int left = 0, right = s.length - 1;
        while(left <= right){
            char temp = s[left];
            s[left] = s[right];
            s[right] = temp;
            left++;
            right--;
        }
    }
}
```

---

### 7. Reverse Only Letters (LeetCode 917)

```java
class Solution {
    public String reverseOnlyLetters(String s) {
        char[] arr = s.toCharArray();
        int start = 0, end = arr.length - 1;
        while (start < end) {
            if (Character.isLetter(arr[start]) && Character.isLetter(arr[end])) {
                char temp = arr[start];
                arr[start] = arr[end];
                arr[end] = temp;
                start++;
                end--;
            } else if (!Character.isLetter(arr[start])) {
                start++;
            } else {
                end--;
            }
        }
        return new String(arr);
    }
}
```

---

### 8. Reverse Vowels of a String (LeetCode 345)

```java
class Solution {
    public String reverseVowels(String s) {
        int left = 0, right = s.length() - 1;
        char arr[] = s.toCharArray();
        String vow = "aeiouAEIOU";
        while(left <= right){
            if(vow.indexOf(s.charAt(left)) != -1 && vow.indexOf(s.charAt(right)) != -1){
                char ch = arr[left];
                arr[left] = arr[right];
                arr[right] = ch;
                left++;
                right--;
            }
            else if(vow.indexOf(s.charAt(left)) == -1 && vow.indexOf(s.charAt(right)) != -1) left++;
            else right--;
        }
        String ans = new String(arr);
        return ans;
    }
}
```
