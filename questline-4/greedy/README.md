# Greedy Algorithms: Lemonade Change & Assign Cookies

## Problem: Lemonade Change (LeetCode 860)

### Intuition & Approach
Each lemonade costs $5. Customers pay with either $5, $10, or $20 bills. We need to provide the exact change immediately to every customer.

We use a **Greedy Approach** by keeping track of the count of `$5` and `$10` bills in our register:
- **$5 Bill**: No change needed. Increment the `$5` count.
- **$10 Bill**: Requires $5 change. Give one `$5` bill. If unavailable, return `false`.
- **$20 Bill**: Requires $15 change. We prioritize giving **one $10 bill + one $5 bill** over **three $5 bills**. 

### Why the Greedy Choice Works
The `$5` bill is strictly more versatile than the `$10` bill because it can be used to give change for both `$10` and `$20` transactions. Saving `$5` bills for as long as possible prevents running out of change for future `$10` bills.

### Complexity Analysis
- **Time Complexity**: $O(n)$, where $n$ is the number of customers. We make a single pass through the array.
- **Space Complexity**: $O(1)$, using only two integer variables (`fives` and `tens`).