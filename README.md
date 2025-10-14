# TJ Tasks 2025 – Adarsh Srivastava
### DSA | Beginner / Easy Level Problems

This repository contains solutions to three fundamental **Data Structures & Algorithms** problems.  
Each problem focuses on logic building, mathematical reasoning, and efficient implementation in code.

---

## Question 1: Minimum Operations to Make Product Positive  

### Problem Overview  
You are given an array of integers. Your task is to determine the **minimum number of operations** required to make the **product of all elements positive**.

### Logic Used  
1. **Count Zeros and Negatives:**  
   - Traverse the array and count how many elements are `0` and how many are negative (`< 0`).  

2. **Handle Zero Elements:**  
   - Each `0` must be converted to `1` → each conversion counts as one operation.  

3. **Check Parity of Negatives:**  
   - If the number of negatives is even → product is already positive.  
   - If odd → flip one negative to positive (requires 1 extra operation).  

4. **Total Operations:**  
   ```
   total_ops = zeros + (negatives are odd ? 1 : 0)
   ```
   
5. **Print the Result** for each test case.

---

## Question 2: Sum of Alternating Sequence  

### Problem Overview  
For given integers `x` and `n`, you need to compute the **sum of an alternating sequence** according to given conditions.

### Logic Used  
1. Read number of test cases `t`.  
2. For each test case, take input values `x` and `n`.  
3. Apply logic:  
   - If `n` is even → the sum of the sequence = `0`.  
   - If `n` is odd → the sum = `x`.  
4. Print the result for every test case.

---

## Question 3: Trippi Troppi’s World  

### Problem Overview  
Given three words for each test case, form a **modern name** by using the initials.

### Logic Used  
1. Input total number of test cases `t`.  
2. For each test case, read three space-separated words.  
3. Take the **first character** from each word.  
4. Concatenate them to form the result (modern name).  
5. Print the final output.

---

## Example Output (for illustration)
```
Input:
3
-1 0 2
4 5
adarsh srivastava tj

Output:
2
0
amt
```
# Vibe Coding Challenges

Welcome to **Vibe Coding**! These challenges are designed to sharpen your web development skills while keeping things fun and interactive. Complete them to showcase your coding vibe.  

---

## Challenge 1: Tic Tac Toe – Quick & Clean (Easy)

**Objective:**  
Build a fully playable Tic Tac Toe game in **one HTML file**.

**Requirements:**  
- Use **HTML, CSS, and JavaScript** only.  
- Display a **3x3 grid** for two players.  
- Implement **turn tracking** and show **current player**.  
- Detect **wins, draws**, and **highlight the winning combination**.  
- Include a **“Replay” button** – no page refresh required.  
- Keep code **self-contained** and **ready to run**.  
- Bonus: add **comments** to explain your logic.  

**Expected Result:**  
Open in a browser → play instantly → see the vibe.  

---

## Challenge 2: Real-Time Chat – Connected & Smooth (Medium)

**Objective:**  
Create a **live multi-user chat app** with backend storage.

**Requirements:**  
- **Frontend:** Clean UI showing **user names, timestamps, and messages**.  
- **Backend:** API to **store and retrieve messages**.  
- Real-time updates using **WebSockets** or **polling**.  
- Ensure **multi-user messaging works seamlessly**.  
- Write **readable code**, using **traditional loops** where appropriate.  
- Document your creation in a **.txt file**, showing **step-by-step prompt chaining**.  
- Optional: integrate **AI agents or prompt chaining** to enhance features.  

**Expected Result:**  
Fully deployed chat app → multiple users chatting live → smooth vibe.  

---

## Author
**Adarsh Srivastava**  
*Data Structures & Algorithms | TJ Tasks 2025*
