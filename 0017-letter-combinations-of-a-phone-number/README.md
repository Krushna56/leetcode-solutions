# 17. Letter Combinations of a Phone Number

**Difficulty:** Medium  
**Topics:** Hash Table, String, Backtracking  
**Problem:** [leetcode.com/problems/letter-combinations-of-a-phone-number](https://leetcode.com/problems/letter-combinations-of-a-phone-number/)

## Intuition

The problem asks for every possible string that can be formed by picking one letter for each digit on a classic phone keypad. Since each digit has a small, fixed set of letters, the natural way to explore all possibilities is depth‑first search (backtracking): build the string one character at a time, and when the current length equals the number of input digits, record the completed combination.

## Approach

1. **Handle empty input** – if the digit string is empty, return an empty list immediately.  
2. **Map digits to letters** – store the standard phone‑pad mapping in a dictionary for quick lookup.  
3. **Define a recursive helper `backtrack(index, path)`**  
   - `index` indicates the position in the input digit string we are currently processing.  
   - `path` is a mutable list holding the characters chosen so far.  
4. **Base case** – when `index` equals the length of `digits`, join the characters in `path` into a string and append it to the result list.  
5. **Recursive case** – retrieve the possible letters for `digits[index]`. For each letter:  
   - Append the letter to `path`.  
   - Recurse with `index + 1`.  
   - After returning, remove the last letter (`pop`) to backtrack and try the next option.  
6. **Kick off recursion** with `backtrack(0, [])`.  
7. **Return** the collected list of combinations.

## Complexity

- Time: $$O(4^n \cdot n)$$
- Space: $$O(n)$$

---
<sub>Synced with [SQLens](https://www.practicemysql.com/faq.html)</sub>
