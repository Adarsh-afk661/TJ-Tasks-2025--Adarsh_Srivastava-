# TJ-Tasks-2025--Adarsh_Srivastava-

Question 1->
Minimum Operations to Make Product Positive? Code is in file.

Algorithm:
Count zeros and -1s:

Loop through the array.
Let zeros = number of 0s, neg = number of -1s.
Handle zeros:

Each zero must become 1 → zeros operations.
Check negative count:

If neg is even, the product of negatives is already positive.
If neg is odd, flip one -1 to make the product positive.
Calculate total operations:

ops = zeros + neg (each -1 requires 1 operation to flip partially)
If neg is odd → add 1 extra operation to handle the odd negative.
Print result:
