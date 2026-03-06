# Lexicographical String – Approach Explanation

To find the **smallest lexicographical string based on a custom alphabet order**, we follow these steps.

---

## Python Logic

```python
test = int(input())

while test > 0:
    P = input()
    S = input()

    list1 = []

    for i in S:
        list1.append(P.find(i))

    list1.sort()

    for i in list1:
        print(P[i], end="")

    if test > 1:
        print()

    test -= 1

```
## Example
Custom Alphabet Order
P = polikujmnhytgbvfredcxswqaz

Each character has a position (index) in this custom order.

## Example indices:

Character	Index in P

b	13
d	18
c	19
a	24

Input String

S = abcd

Step 1: Find Index of Each Character in P

a → 24
b → 13
c → 19
d → 18

So the list becomes:

List1 = [24, 13, 19, 18]

Step 2: Sort the Index Values

List1 = [13, 18, 19, 24]

Step 3: Print Characters Using Sorted Index
P[13] = b
P[18] = d
P[19] = c
P[24] = a
Final Output
bdca
