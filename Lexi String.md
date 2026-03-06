# Question 01 – Smallest Lexicographical String

## Problem Statement

Little Jill jumbled up the order of the letters in our dictionary. Now, Jack uses this list to find the **smallest lexicographical string** that can be made out of this new order.

You are given a string **P** that denotes the **new order of the letters in the English dictionary**.

You need to print the **smallest lexicographic string made from the given string S** according to the order defined in **P**.

---

## Constraints

- `1 ≤ T ≤ 1000`
- `Length(P) = 26`
- `1 ≤ length(S) ≤ 100`
- All characters in strings **S** and **P** are lowercase.

---

## Input Format

1. The first line contains the number of test cases **T**.
2. The second line contains the string **P** representing the new alphabet order.
3. The third line contains the string **S**.

For multiple test cases, the last two lines repeat.

---

## Output Format

Print a **single string in a new line for every test case** giving the result.

---

## Example

### Input
2

polikujmnhytgbvfredcxswqaz

abcd

qwryupcsfoghjkldezvxbintma

ativedoc

### Output
bdca

codevita


---

## Explanation

For each test case:

1. The string **P** represents a **custom alphabetical order**.
2. Rearrange the characters in **S** based on the order defined in **P**.
3. The result should be the **smallest lexicographical string according to this custom order**.

---
