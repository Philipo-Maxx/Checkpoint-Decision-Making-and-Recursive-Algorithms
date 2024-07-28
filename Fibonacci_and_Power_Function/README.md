# Algorithms: Fibonacci and Power Function

## Overview

This document provides explanations for two recursive algorithms: the Fibonacci sequence and the Power function. Each function is implemented using recursion, demonstrating how recursive calls can break down problems into simpler subproblems.

## Table of Contents

1. [Fibonacci Function](#fibonacci-function)
2. [Power Function](#power-function)

## Fibonacci Function

### Description

The Fibonacci function computes the nth Fibonacci number using recursion. The Fibonacci sequence is defined as follows:

- `F(0) = 0`
- `F(1) = 1`
- For `n >= 2`, `F(n) = F(n - 1) + F(n - 2)`

### Algorithm Steps

1. **Base Case for `n = 0`:**

   - If `n` is `0`, return `0`. This handles the simplest case of the Fibonacci sequence.

2. **Base Case for `n = 1`:**

   - If `n` is `1`, return `1`. This is the next simplest case in the sequence.

3. **Recursive Case:**
   - For `n >= 2`, compute the Fibonacci number by summing the results of two recursive calls:
     - `fibonacci(n - 1)`
     - `fibonacci(n - 2)`
   - Return the sum of these two calls to get the Fibonacci number at position `n`.

### Recursive Formula

```plaintext
FUNCTION fibonacci(n: INTEGER): INTEGER
VAR
    result: INTEGER
BEGIN
    IF n = 0 THEN
        RETURN result := 0
    ELSE IF n = 1 THEN
        RETURN result := 1
    ELSE
        RETURN result := fibonacci(n - 1) + fibonacci(n - 2)
    END_IF

    RETURN result
END
```

### Example

- **Input:** `fibonacci(5)`
- **Execution:**
  1. `fibonacci(5)` calls `fibonacci(4)` and `fibonacci(3)`
  2. `fibonacci(4)` calls `fibonacci(3)` and `fibonacci(2)`
  3. `fibonacci(3)` calls `fibonacci(2)` and `fibonacci(1)`
  4. `fibonacci(2)` calls `fibonacci(1)` and `fibonacci(0)`
  5. Base cases are reached: `fibonacci(1) = 1` and `fibonacci(0) = 0`
  6. Results are combined as follows:
     - `fibonacci(2) = fibonacci(1) + fibonacci(0) = 1 + 0 = 1`
     - `fibonacci(3) = fibonacci(2) + fibonacci(1) = 1 + 1 = 2`
     - `fibonacci(4) = fibonacci(3) + fibonacci(2) = 2 + 1 = 3`
     - `fibonacci(5) = fibonacci(4) + fibonacci(3) = 3 + 2 = 5`
- **Output:** `5`

### Complexity

- **Time Complexity:** `O(2^n)` — Exponential time complexity due to the repeated calculation of the same values.
- **Space Complexity:** `O(n)` — Linear space complexity due to the recursion stack.

## Power Function

### Description

The Power function calculates the result of raising a base to an exponent using recursion. It handles positive exponents, zero exponent, and negative exponents.

### Algorithm Steps

1. **Base Case for `exponent = 0`:**

   - If `exponent` is `0`, return `1`. This is because any number raised to the power of `0` is `1`.

2. **Recursive Case for Positive Exponents:**

   - If `exponent` is greater than `0`, compute the power by multiplying the base with the result of a recursive call:
     - `power(base, exponent - 1)`
   - Return the product of the base and the result of the recursive call.

3. **Recursive Case for Negative Exponents:**
   - If `exponent` is less than `0`, compute the power by recursively calculating `power(base, -exponent)` and then taking the reciprocal of the result.

### Recursive Formula

```plaintext
FUNCTION power(base: INTEGER, exponent: INTEGER): INTEGER
VAR
    result: INTEGER
BEGIN
    IF exponent = 0 THEN
        RETURN result := 1
    ELSE IF exponent > 0 THEN
        RETURN result := base * power(base, exponent - 1)
    ELSE
        RETURN result := 1 / power(base, -exponent) // Handling negative exponents if needed
    END_IF

    RETURN result
END
```

### Example

- **Input:** `power(2, 3)`
- **Execution:**
  1. `power(2, 3)` calls `power(2, 2)`
  2. `power(2, 2)` calls `power(2, 1)`
  3. `power(2, 1)` calls `power(2, 0)`
  4. Base case returns `1`, so:
     - `power(2, 1)` returns `2 * 1 = 2`
     - `power(2, 2)` returns `2 * 2 = 4`
     - `power(2, 3)` returns `2 * 4 = 8`
- **Output:** `8`

- **Input:** `power(2, -3)`
- **Execution:**
  1. `power(2, -3)` computes `1 / power(2, 3)`
  2. `power(2, 3)` is `8`, so:
     - `power(2, -3)` returns `1 / 8 = 0.125`
- **Output:** `0.125`

### Complexity

- **Time Complexity:** `O(exponent)` — Linear time complexity due to the recursion depth.
- **Space Complexity:** `O(exponent)` — Linear space complexity due to the recursion stack.

## Usage

To use these functions in your program:

1. **Fibonacci Function:** Call the function with an integer `n` to compute the nth Fibonacci number. Ensure that the input `n` is non-negative.
2. **Power Function:** Call the function with a `base` and `exponent` to compute the result of raising the base to the exponent. It handles positive, zero, and negative exponents.

---

This `README.md` file provides a comprehensive explanation of the Fibonacci and Power functions, including their purposes, steps, and examples. It includes details on how each function works and its complexity, helping users understand and utilize these algorithms effectively.
