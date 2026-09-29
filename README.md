# Lab 3: Asymptotic Analysis

This lab focuses on understanding and analyzing the asymptotic behavior of algorithms. We will explore concepts such as Big-O, Big-$\Theta$, and Big-$\Omega$ notations, and apply them to various algorithmic problems to determine their efficiency and scalability.

**Instructions:** To complete this lab, you may work in groups, but you must write your solutions yourself. Once you have completed the lab, push your changes to your forked repository.

## Problem 1

Suppose $T(n)$ is the worst case running time of an algorithm with input size $n$, and we know that $T(n)$ is $\mathcal{O}(n^3)$ and $\Omega(n^2)$. For each of the following statements, determine whether it must be true, must be false, or could be either true or false. Give a brief justification for each. 

1. $T(n)$ is $\mathcal{O}(n^2)$.

- Either; If T(n) = n^2, then it is O(n^2). If T(n) = n^3, then it is not O(n^2). Therefore, it could be either true or false.

2. $T(n)$ is $\Theta(n^3)$.

- True; If T(n) = n^3, then it is Theta(n^3). If T(n) = n^2, then it is not Theta(n^3). The given information does not guarantee Theta(n^3).

3. $T(n)$ is $\Omega(n)$.

- False; Since T(n) is Omega(n^2), it must also be Omega(n) because n^2 grows at least as fast as n.

4. $T(n)$ is $\Theta(n^{1.5})$.

- False; Theta(n^1.5) grows slower than n^2. Since T(n) is Omega(n^2), it cannot be Theta(n^1.5).

5. $T(n)$ is $\mathcal{O}(n)$.

- True; A function that is Omega(n^2) cannot also be O(n) because n^2 grows faster than n.

6. $T(n)$ is $\Theta(n^2 \log n)$.

- Either; n^2 log n satisfies both O(n^3) and Omega(n^2), so T(n) could be Theta(n^2 log n). However, T(n) could also be n^2 or n^3, so it is not guaranteed.

## Problem 2
Consider the following algorithm where $f(A, i, j)$ is an unknown algorithm that takes as input an array $A$ and two indicies $i$ and $j$ and returns a number. \

```
Mystery Algorithm
Input: An array of int $A$ of length $n$.
Output: int sum
    n = |A|
    sum = 0
    for i = 1 to n:
        for j = 1 to n:
            sum += f(A, i, j)
```

Without knowing anything about $f$, what can we say about the running time of the Mystery Algorithm in terms of $n$? Justify your answer.

Answer:

The running time of the Mystery Algorithm depends on the running time of f(A, i, j). The algorithm contains two nested loops, and each loop runs n times. Therefore, f(A, i, j) is called n^2 times.

If the running time of f is T_f, then the total running time of the algorithm is Theta(n^2 * T_f).

Since we are not given any information about f, we cannot determine the exact running time as a function of n alone. We can only conclude that the algorithm makes n^2 calls to f.