# Move Zeroes - Different Approaches in Java

Here is the full Java code for three different approaches to move all zeroes in an array to the end while maintaining the order of non-zero elements.

---

## 1. Simple Approach (Using Extra Space)

This is the easiest to write because it avoids complex index management by using a temporary array.

**Complexity:** Time O(n), Space O(n)

```java
import java.util.Arrays;

public class MoveZeroesSimple {
    public static void main(String[] args) {
        int[] arr = {0, 1, 0, 3, 12};
        int n = arr.length;
        int[] temp = new int[n]; // New array initialized with 0s
        int j = 0;

        // Copy non-zero elements to temp array
        for (int i = 0; i < n; i++) {
            if (arr[i] != 0) {
                temp[j++] = arr[i];
            }
        }

        System.out.println("Result: " + Arrays.toString(temp));
    }
}
```
## 2. Two-Pass Approach (Standard In-Place)

This is the most common textbook solution. It modifies the array in two steps without using extra memory.

**Complexity:** Time O(n), Space O(1)

```java
public class MoveZeroesTwoPass {
    public static void main(String[] args) {
        int[] arr = {0, 1, 0, 3, 12};
        int n = arr.length;
        int count = 0;

        // Pass 1: Shift non-zeroes to the front
        for (int i = 0; i < n; i++) {
            if (arr[i] != 0) {
                arr[count++] = arr[i];
            }
        }

        // Pass 2: Fill remaining positions with zeroes
        while (count < n) {
            arr[count++] = 0;
        }

        for (int i : arr) {
            System.out.print(i + " ");
        }
    }
}
```
## 3. Best Approach: One-Pass Swap (Most Efficient)

This is the optimal way used in professional coding and interviews. It rearranges elements in a single traversal.

**Complexity:** Time O(n), Space O(1)

```java
public class MoveZeroesBest {
    public static void main(String[] args) {
        int[] arr = {0, 1, 0, 3, 12};
        int n = arr.length;
        int j = 0; // Pointer for the next non-zero position

        for (int i = 0; i < n; i++) {
            // If current element is non-zero, swap it with element at index j
            if (arr[i] != 0) {
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
                j++;
            }
        }

        for (int i : arr) {
            System.out.print(i + " ");
        }
    }
}
```
