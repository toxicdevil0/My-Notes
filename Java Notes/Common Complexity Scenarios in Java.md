

This lesson summarizes common complexity measures and includes some commonly used examples and handy formulas to help you with your interview.

  

## List of Important Complexities

  

Let's study some common examples and handy formulas for solving time complexity problems in Java.

  

The following list shows some common loop statements and how much time they take to execute.

  

---

  

## Simple for-loop

  

```java

for (int x = 0; x < n; x++) {

    // statement(s) that take constant time

}

```

  

**Running Time Complexity:** \( n = O(n) \)

  

**Explanation:**

Java's `for` loop with `x = 0; x < n; x++` runs the loop body exactly `n` times, incrementing `x` by 1 each time. Each iteration takes constant time, so the total time is proportional to `n`.

  

---

  

## For-loop with Increments

  

```java

for (int x = 1; x < n; x += k) {

    // statement(s) that take constant time

}

```

  

**Running Time Complexity:** \( \left\lfloor \frac{n}{k} \right\rfloor = O(n) \)

  

**Explanation:**

Here, `x` starts at 1 and increases by `k` each time until it reaches or exceeds `n`. The loop runs about `n / k` times, which is still O(n) for constant `k`.

  

---

  

## Simple Nested For-loop

  

```java

for (int i = 0; i < n; i++) {

    for (int j = 0; j < m; j++) {

        // statement(s) that take constant time

    }

}

```

  

**Running Time Complexity:** \( n \times m = O(nm) \)

  

**Explanation:**

The outer loop runs `n` times, and for each iteration, the inner loop runs `m` times. So the total number of iterations is `n * m`.

  

---

  

## Nested For-loop with Dependent Variables

  

```java

for (int i = 0; i < n; i++) {

    for (int j = 0; j < i; j++) {

        // statement(s) that take constant time

    }

}

```

  

**Running Time Complexity:** \( \frac{n(n-1)}{2} = O(n^2) \)

  

**Explanation:**

The inner loop runs `i` times for each `i` from 0 to `n-1`. The total number of iterations is the sum `1 + 2 + ... + (n-1) = n(n-1)/2`, which is O(n²).

  

---

  

## Nested For-loop with Index Modification

  

```java

for (int i = 0; i < n; i++) {

    i *= 2;

    for (int j = 0; j < n; j++) {

        // statement(s) that take constant time

    }

}

```

  

**Running Time Complexity:** \( n(n-1) = n^2 - n = O(n^2) \)

  

**Explanation:**

The outer loop modifies `i` by multiplying by 2 each time, so it runs about log₂(n) times. The inner loop runs `n` times for each outer iteration, so the total is O(n log n) if the inner loop is inside the modified outer loop. (Note: The code above as written will skip some values of `i` due to `i *= 2`.)

  

---

  

## Loops with log(n) Time Complexity

  

```java

int i = 1;

int n = ...; // some constant

int k = 2;   // some constant

while (i < n) {

    i *= k;

    // statement(s) that take constant time

}

```

  

**Running Time Complexity:** \( \log_k(n) = O(\log_k(n)) \)

  

**Explanation:**

A loop that multiplies or divides the loop variable by a constant each time runs in logarithmic time. For example, if `i` doubles each time and `n = 16`, the loop runs 4 times (since 2⁴ = 16).

  

---

  

Feel free to try these examples in Java to see how the number of iterations changes with different values of `n` and `k`!