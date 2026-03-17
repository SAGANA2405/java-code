# Feb 26 - Advanced Matrix Operations

### 1. Check whether matrix is Toeplitz
**Input Format:** Number of rows, Number of columns, Matrix elements  
**Output Format:** Toeplitz matrix / Not a Toeplitz matrix

```java
import java.util.*;
public class demo{
    public static void main(String args[]){
        Scanner ob = new Scanner(System.in);
        int a = ob.nextInt();
        int b = ob.nextInt();
        int arr[][] = new int[a][b];
        int i, j;
        for(i = 0; i < a; i++){
            for(j = 0; j < b; j++){
                arr[i][j] = ob.nextInt();
            }
        }
        for(i = 0; i < a - 1; i++){
            for(j = 0; j < b - 1; j++){
                if(arr[i][j] != arr[i+1][j+1]){
                    System.out.print("Not a Toeplitz matrix");
                    return;
                }
            }
        }
        System.out.println("Toeplitz matrix");
    }
}
```

---

### 2. Check whether the matrix is a diagonal matrix
**Input Format:** Size of matrix, Matrix Elements  
**Output Format:** Diagonal matrix / Not a Diagonal matrix

```java
import java.util.*;
public class demo{
    public static void main(String args[]){
        Scanner ob = new Scanner(System.in);
        int a = ob.nextInt();
        int b = a;
        int arr[][] = new int[a][b];
        int i, j;
        for(i = 0; i < a; i++){
            for(j = 0; j < b; j++){
                arr[i][j] = ob.nextInt();
            }
        }
        for(i = 0; i < a - 1; i++){
            for(j = 0; j < b - 1; j++){
                if(i != j && arr[i][j] != 0){
                    System.out.print("Not a Diagonal matrix");
                    return;
                }
            }
        }
        System.out.println("Diagonal matrix");
    }
}
```

---

### 3. Check whether the matrix is an identity matrix

```java
import java.util.*;
public class demo{
    public static void main(String args[]){
        Scanner ob = new Scanner(System.in);
        int a = ob.nextInt();
        int b = a;
        int arr[][] = new int[a][b];
        int i, j;
        for(i = 0; i < a; i++){
            for(j = 0; j < b; j++){
                arr[i][j] = ob.nextInt();
            }
        }
        for(i = 0; i < a; i++){
            for(j = 0; j < b; j++){
                if((i != j && arr[i][j] != 0) || (i == j && arr[i][j] != 1)){
                    System.out.print("Not an Identity matrix");
                    return;
                }
            }
        }
        System.out.println("Identity matrix");
    }
}
```

---

### 4. Create transpose of a matrix

```java
import java.util.*;
public class demo{
    public static void main(String args[]){
        Scanner ob = new Scanner(System.in);
        int a = ob.nextInt();
        int b = a;
        int arr[][] = new int[a][b];
        int i, j;
        for(i = 0; i < a; i++){
            for(j = 0; j < b; j++){
                arr[i][j] = ob.nextInt();
            }
        }
        for(i = 0; i < a; i++){
            for(j = 0; j < b; j++){
                System.out.print(arr[j][i] + " ");
            }
            System.out.println();
        }
    }
}
```

---

### 5. Sum of lower triangular matrix

```java
import java.util.*;
public class demo{
    public static void main(String args[]){
        Scanner ob = new Scanner(System.in);
        int a = ob.nextInt();
        int b = a;
        int arr[][] = new int[a][b];
        int i, j;
        for(i = 0; i < a; i++){
            for(j = 0; j < b; j++){
                arr[i][j] = ob.nextInt();
            }
        }
        int sum = 0;
        for(i = 0; i < a; i++){
            for(j = 0; j <= i; j++){
                sum += arr[i][j];
            }
        }
        System.out.println(sum);
    }
}
```

---

### 6. Print the boundary elements in the matrix

```java
import java.util.*;
public class demo{
    public static void main(String args[]){
        Scanner ob = new Scanner(System.in);
        int a = ob.nextInt();
        int b = ob.nextInt();
        int arr[][] = new int[a][b];
        int i, j;
        for(i = 0; i < a; i++){
            for(j = 0; j < b; j++){
                arr[i][j] = ob.nextInt();
            }
        }
        System.out.print("Upper Boundary:");
        for(i = 0; i < b; i++){
             System.out.print(arr[0][i] + " ");
        }
        System.out.print("\nLower Boundary:");
        for(i = 0; i < b; i++){
            System.out.print(arr[a-1][i] + " ");
        }
        System.out.print("\nLeft Boundary:");
        for(i = 0; i < a; i++){
            System.out.print(arr[i][0] + " ");
        }
        System.out.print("\nRight Boundary:");
        for(i = 0; i < a; i++){
            System.out.print(arr[i][b-1] + " ");
        }
    }
}
```

---

### 7. Check whether matrix is a sparse matrix
*In a sparse matrix, more than half the elements are zero.*

```java
import java.util.*;
public class demo{
    public static void main(String args[]){
        Scanner ob = new Scanner(System.in);
        int a = ob.nextInt();
        int b = ob.nextInt();
        int arr[][] = new int[a][b];
        int i, j;
        for(i = 0; i < a; i++){
            for(j = 0; j < b; j++){
                arr[i][j] = ob.nextInt();
            }
        }
        int zero = 0, nonzero = 0;
        for(i = 0; i < a; i++){
            for(j = 0; j < b; j++){
                if(arr[i][j] == 0){
                    zero++;
                } else {
                    nonzero++;
                }
            }
        }
        if(zero < nonzero){
            System.out.println("Not a Sparse Matrix");
        } else {
            System.out.println("Sparse Matrix");
        }
    }
}
```

---

### 8. Check whether the given matrix is a scalar matrix

```java
import java.util.*;
public class demo{
    public static void main(String args[]){
        Scanner ob = new Scanner(System.in);
        int a = ob.nextInt();
        int b = ob.nextInt();
        int arr[][] = new int[a][b];
        int i, j;
        for(i = 0; i < a; i++){
            for(j = 0; j < b; j++){
                arr[i][j] = ob.nextInt();
            }
        }
        for(i = 0; i < a; i++){
            for(j = 0; j < b; j++){
                if((i != j && arr[i][j] != 0) || (i == j && arr[i][j] != arr[0][0])){
                    System.out.print("Not a scalar matrix");
                    return;
                }
            }
        }
        System.out.println("Scalar matrix");
    }
}
```

---

### 9. Transpose the matrix and perform difference with original

```java
import java.util.*;
public class demo{
    public static void main(String args[]){
        Scanner ob = new Scanner(System.in);
        int a = ob.nextInt();
        int b = ob.nextInt();
        int arr[][] = new int[a][b];
        int i, j;
        for(i = 0; i < a; i++){
            for(j = 0; j < b; j++){
                arr[i][j] = ob.nextInt();
            }
        }
        if(a != b){
            System.out.println("Subtraction cannot be performed for rectangular matrix");
            return;
        }
        int arr1[][] = new int[b][a];
        for(i = 0; i < a; i++){
            for(j = 0; j < b; j++){
                arr1[i][j] = arr[j][i];
            }
        }
        for(i = 0; i < a; i++){
            for(j = 0; j < b; j++){
                System.out.print(arr[i][j] - arr1[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

---

### 10. Transpose the matrix and perform addition with original

```java
import java.util.*;
public class demo{
    public static void main(String args[]){
        Scanner ob = new Scanner(System.in);
        int a = ob.nextInt();
        int b = ob.nextInt();
        int arr[][] = new int[a][b];
        int i, j;
        for(i = 0; i < a; i++){
            for(j = 0; j < b; j++){
                arr[i][j] = ob.nextInt();
            }
        }
        if(a != b){
            System.out.println("Sum cannot be performed for rectangular matrix");
            return;
        }
        int tran[][] = new int[a][b];
        for(i = 0; i < a; i++){
            for(j = 0; j < b; j++){
                tran[i][j] = arr[j][i];
            }
        }
        for(i = 0; i < a; i++){
            for(j = 0; j < b; j++){
                System.out.printf("%02d", arr[i][j] + tran[i][j]);
                System.out.print(" ");
            }
            System.out.println();
        }
    }
}
```
