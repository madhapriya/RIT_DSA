# One's Complement Logic in Python

Here is the breakdown of different approaches to compute the One's Complement of a number in Python, from a mathematical approach to the most optimized Pythonic solution.

---

## 1. Step 1: Math Approach

This approach uses `math.log2()` to determine how many bits the number contains.  
While correct, it requires the `math` library and can sometimes face precision issues with extremely large numbers.

**Complexity:** Time O(1)

```python
import math

n = int(input())

if n == 0:
    print(1)
else:
    # (1 << bits) creates a power of 2, subtracting 1 makes it all 1s
    k = (1 << int(math.log2(n)) + 1) - 1
    print(n ^ k)
```
## 2. Step 2: Better Logic (While Loop)

This approach avoids the math library completely.  
It finds the smallest power of 2 greater than `n` using a loop.

**Complexity:** Time O(bits)

```python
n = int(input())

if n == 0:
    print(1)
else:
    mask = 1

    while mask <= n:
        mask <<= 1  # Shift left until mask is greater than n

    mask -= 1  # Example: if mask was 8 (1000), it becomes 7 (111)

    print(n ^ mask)
```
## 3. Step 3: Best Logic (bit_length)

This is the most Pythonic and efficient method.  
The `.bit_length()` method directly returns the number of bits required to represent the integer.

**Complexity:** Time O(1)

```python
n = int(input())

if n == 0:
    print(1)
else:
    # 1 << n.bit_length() creates the next power of 2
    mask = (1 << n.bit_length()) - 1
    print(n ^ mask)
```
