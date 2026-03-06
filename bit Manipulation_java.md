# One's Complement of a Number - Different Approaches in Java

To find the One's Complement (flipping 0 to 1 and 1 to 0) of a number's binary representation, here are three different approaches from simplest to most efficient.

---

## 1. Simple Logic (String Manipulation)

This is very intuitive but slightly slower due to string operations. It converts the number to binary, flips the characters, and converts back.

**Logic:** Decimal → Binary String → Flip characters → Decimal  
**Complexity:** Time O(n), Space O(n)

```java
import java.util.Scanner;

public class ComplementSimple {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        
        if (n == 0) { 
            System.out.println(1); 
            return; 
        }

        String bin = Integer.toBinaryString(n);
        StringBuilder flipped = new StringBuilder();

        for (char c : bin.toCharArray()) {
            flipped.append(c == '0' ? '1' : '0');
        }

        int res = Integer.parseInt(flipped.toString(), 2);
        System.out.println(res);
    }
}
```
## 2. Better Logic (String Swapping)

This approach swaps the values using `replace`. It uses a temporary character to avoid overwriting values.

**Logic:** Replace 1 → 2, 0 → 1, then 2 → 0  
**Complexity:** Time O(n), Space O(n)

```java
import java.util.Scanner;

public class ComplementBetter {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int no = sc.nextInt();

        if (no == 0) {
            System.out.println(1);
            return;
        }

        String bin = Integer.toBinaryString(no);

        // Swap 1->2, 0->1, 2->0
        bin = bin.replace('1', '2').replace('0', '1').replace('2', '0');

        System.out.println(Integer.parseInt(bin, 2));
    }
}

```
## 3. Best Logic (Bitwise XOR Mask)

This is the optimal approach used in competitive programming. Instead of strings, it uses bitwise operations.

**Logic:**
1. Find the number of bits in the number.
2. Create a mask of all 1s.
3. XOR the number with the mask to flip all bits.

**Complexity:** Time O(1), Space O(1)

```java
import java.util.Scanner;

public class ComplementBest {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();

        if (n == 0) {
            System.out.println(1);
            return;
        }

        // Step 1: Find how many bits the number has
        int bitCount = (int)(Math.log(n) / Math.log(2)) + 1;

        // Step 2: Create a mask of all 1s
        int mask = (1 << bitCount) - 1;

        // Step 3: XOR flips the bits
        int result = n ^ mask;

        System.out.println(result);
    }
}


```
