# Feb 27 - Matrix Patterns & Math

### 1. Display Number Pattern
**Input Format:** Integer `n`  
**Output Format:** Concentric square pattern

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int m = n * 2 - 1;
        int arr[][] = new int[m][m];
        int top = 0, bot = m - 1, left = 0, right = m - 1, i, j, val = n;
        
        while(top <= bot){
            for(i = left; i <= right; i++)
                arr[top][i] = val;
            top++;
            for(i = top; i <= bot; i++)
                arr[i][right] = val;
            right--;
            for(i = right; i >= left; i--)
                arr[bot][i] = val;
            bot--;
            for(i = bot; i >= top; i--)
                arr[i][left] = val;
            left++;
            val--;
        }
        for(i = 0; i < m; i++){
            for(j = 0; j < m; j++){
                System.out.print(arr[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

---

### 2. Spiral Pattern
**Input Format:** Integer `n`  
**Output Format:** Spiral numbering in a 2D matrix

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int arr[][] = new int[n][n];
        int top = 0, bot = n - 1, left = 0, right = n - 1, i, j, val = 1;
        
        while(top <= bot){
            for(i = left; i <= right; i++)
                arr[top][i] = val++;
            top++;
            for(i = top; i <= bot; i++)
                arr[i][right] = val++;
            right--;
            for(i = right; i >= left; i--)
                arr[bot][i] = val++;
            bot--;
            for(i = bot; i >= top; i--)
                arr[i][left] = val++;
            left++;
        }
        for(i = 0; i < n; i++){
            for(j = 0; j < n; j++){
                System.out.print(arr[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

---

### 3. Multiply Two Matrices

```java
import java.io.*;
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int i, j, row = sc.nextInt();
        int col = sc.nextInt();
        int arr1[][] = new int[row][col];
        int arr2[][] = new int[row][col];
        
        for(i = 0; i < row; i++){
            for(j = 0; j < col; j++){
                arr1[i][j] = sc.nextInt();
            }
        }
        for(i = 0; i < row; i++){
            for(j = 0; j < col; j++){
                arr2[i][j] = sc.nextInt();
            }
        }
        for(i = 0; i < row; i++){
            for(j = 0; j < col; j++){
                int sum = 0;
                for(int k = 0; k < row; k++){
                    sum += (arr1[i][k] * arr2[k][j]);
                }
                System.out.print(sum + " ");
            }
            System.out.println();
        }
    }
}
```
