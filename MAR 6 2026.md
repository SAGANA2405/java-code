# Mar 6 - Arrays & Running Sums (LeetCode)

### 1. Running Sum of 1D Array
**Problem:** Return the running sum of nums.

```java
class Solution {
    public int[] runningSum(int[] nums) {
      int n = nums.length;
      int[] ans = new int[n];
      for(int i = 0; i < n; i++) {
        int sum = 0;
        for(int j = 0; j <= i; j++) {
            sum += nums[j];
        }
        ans[i] = sum;
      }
      return ans;
    }
}
```

---

### 2. Concatenation of Array
**Problem:** Create an array ans of length 2n where ans[i] == nums[i] and ans[i + n] == nums[i].

```java
class Solution {
    public int[] getConcatenation(int[] nums) {
        int ans[] = new int[nums.length * 2];
        int k = 0;
        for(int i = 0; i < nums.length; i++) {
            ans[k++] = nums[i];
        }
        for(int i = 0; i < nums.length; i++) {
            ans[k++] = nums[i];
        }
        return ans;
    }
}
```

---

### 3. Shuffle the Array
**Problem:** Return the array in the form [x1, y1, x2, y2, ..., xn, yn].

```java
class Solution {
    public int[] shuffle(int[] nums, int n) {
        int[] s = new int[nums.length];
        int k = 0;
        for(int i = 0; i < n; i++) {
            s[k++] = nums[i];
            s[k++] = nums[i+n];
        }
        return s;
    }
}
```

---

### 4. Build Array from Permutation

```java
class Solution {
    public int[] buildArray(int[] nums) {
        int[] ans = new int[nums.length];
        for(int i = 0; i < nums.length; i++) {
            ans[i] = nums[nums[i]];
        }
        return ans;
    }
}
```

---

### 5. Average Value of Even Numbers That Are Divisible by 3

```java
class Solution {
    public int averageValue(int[] nums) {
        int sum = 0;
        int count = 0;
        for(int i = 0; i < nums.length; i++) {
            if(nums[i] % 6 == 0) {
                sum += nums[i];
                count++;
            }
        }
        if(count == 0) {
            return 0;
        }
        return sum / count;
    }
}
```

---

### 6. Difference Between Element Sum and Digit Sum of an Array

```java
class Solution {
    public int differenceOfSum(int[] nums) {
        int elesum = 0;
        int digsum = 0;
        for (int i = 0; i < nums.length; i++) {
            elesum += nums[i];  
            int num = nums[i];
            while (num > 0) {
                digsum += (num % 10);
                num = num / 10;
            }
        }
        return (elesum - digsum);
    }
}
```

---

### 7. How Many Numbers Are Smaller Than the Current Number

```java
class Solution {
    public int[] smallerNumbersThanCurrent(int[] nums) {
        int n = nums.length;
        int[] ans = new int[n];
        for (int i = 0; i < n; i++) {
            int count = 0; 
            for (int j = 0; j < n; j++) {
                if (nums[j] < nums[i]) {
                    count++;
                }
            }
            ans[i] = count;
        }
        return ans;
    }
}
```

---

### 8. Count Elements With Strictly Smaller and Greater Elements

```java
class Solution {
    public int countElements(int[] nums) {
        int min = Integer.MAX_VALUE;
        int max = Integer.MIN_VALUE;
        for(int num : nums) {
            min = Math.min(min, num);
            max = Math.max(max, num);
        }
        int count = 0;
        for(int num : nums) {
            if(num > min && num < max) {
                count++;
            }
        }
        return count;
    }
}
```

---

### 9. Squares of a Sorted Array

```java
import java.util.Arrays;

class Solution {
    public int[] sortedSquares(int[] nums) {
        for(int i = 0; i < nums.length; i++) {
            nums[i] = nums[i] * nums[i];
        }
        Arrays.sort(nums);
        return nums;
    }
}
```

---

### 10. Contains Duplicate

```java
import java.util.Arrays;

class Solution {
    public boolean containsDuplicate(int[] nums) {
        Arrays.sort(nums);
        for(int i = 0; i < nums.length - 1; i++) {
            if(nums[i] == nums[i+1]) {
                return true;
            } 
        }
        return false;
    }
}
```
