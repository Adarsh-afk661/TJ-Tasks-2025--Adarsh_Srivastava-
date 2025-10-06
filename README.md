# TJ-Tasks-2025--Adarsh_Srivastava-
#  Minimum Operations to Make Product Positive

##  Problem  Number 1st

You are given an array `a` of `n` integers, where each element is **−1**, **0**, or **1**.  
In one operation, you can choose an index `i` and **increase** `a[i]` by 1.

That means:
- `-1 → 0 → 1 → 2 → ...`
- `0 → 1 → 2 → ...`

Your goal is to make the **product of all elements strictly positive** (`> 0`)  
using the **minimum number of operations**.

It is guaranteed that this is always possible.

---

## Input Format

---

## Output Format

For each test case, print one integer —  
the **minimum number of operations** required to make the product positive.

---

## Algorithm

1. **Start**  
2. Read integer `t` — number of test cases.  
3. **Repeat** for each test case:  
   1. Read integer `n`.  
   2. Read the array `a` of `n` integers.  
   3. Initialize counters:  
      - `neg = 0` (count of −1 elements)  
      - `zero = 0` (count of 0 elements)  
   4. For each element in the array:  
      - If element == −1 → increment `neg`  
      - If element == 0 → increment `zero`  
   5. If `neg` is **even**:  
      - `operations = zero`  
   6. Else (`neg` is **odd**):  
      - `operations = zero + 2`  
   7. Print `operations`.  
4. **End**

---

## Example

**Input:**

