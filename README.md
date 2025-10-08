# 🌟 TJ-Tasks-2025 — Adarsh Srivastava  
### 📘 Data Structures & Algorithms (Beginner / Easy)

Welcome to **TJ Tasks 2025**, a beginner-friendly DSA challenge set by **Adarsh Srivastava**.  
This collection includes simple yet conceptually strong problems focused on logic building and problem-solving fundamentals.

---

## 🧮 Question 1 — Minimum Operations to Make Product Positive

### 🎯 Objective
Transform the given array so that the **product of all its elements becomes positive** using the fewest possible operations.

---

### ⚙️ Algorithm Steps

1. **Count Zeros and Negatives**
   - Traverse the array.
   - Let:
     - `zeros` = number of elements equal to `0`
     - `neg` = number of negative elements

2. **Handle Zeros**
   - Each `0` must be turned into `1` (since multiplication by `0` results in a product of `0`).
   - So, **`zeros` operations** are needed here.

3. **Balance Negatives**
   - If `neg` is **even**, the product of negatives is already **positive**.
   - If `neg` is **odd**, flip one negative (`-1 → 1`) to make the overall product positive.

4. **Calculate Total Operations**
   ```text
   ops = zeros + number_of_flips
   if neg is odd:
       ops += 1   # one extra operation for balancing the sign
