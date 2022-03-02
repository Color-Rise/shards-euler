# Problem 1: Multiples of 3 or 5

Link to the problem: [https://projecteuler.net/problem=1](https://projecteuler.net/problem=1).

!!! quote "Problem 1"

    If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.

    Find the sum of all the multiples of 3 or 5 below 1000.

## A simple solution

A simple way to do it, is to go through all numbers from $1$ to $999$ and test whether they are divisible by either $3$ or $5$.

=== "Code"

    ```clojure linenums="1"
    --8<-- "src/problems/problem-001a.edn"
    ```

=== "Output"

    ```
    [info] [...] [main-chain] Answer: 233168
    ```

## A better and faster solution

If we are to do the same for all numbers less than $100,000,000$ that is going to take a while.

We can use the fact that the sum of all numbers between $1$ and $p$ can be directly calculated with the following formula:

$$
1 + 2 + 3 +...+ p = \frac{1}{2}p(p + 1)
$$

Adding together all numbers between $1$ and $n$ divisible by $3$ is the same as calculating that sum for all numbers between $1$ and $n/3$ then multiplying the result by $3$.

$$
3 + 6 + 9 +...+ n = 3(1 + 2 + 3 +...+ \frac{n}{3})
$$

The same applies for the numbers divisible by $5$. Then we also need to calculate the same for all numbers that are both divisible by $3$ and $5$ (i.e. divisible by $15$), as they would otherwise be counted twice.

In the end, our calculation is:

$$
\begin{gather}
sumDivisibleBy(x) :=
\begin{cases}
p := \frac{n}{x}\\
\frac{1}{2}p(p + 1)x\\
\end{cases} \\
sum = sumDivisibleBy(3) + sumDivisibleBy(5) - sumDivisibleBy(15)
\end{gather}
$$

=== "Code"

    ```clojure linenums="1"
    --8<-- "src/problems/problem-001b.edn"
    ```

=== "Output"

    ```
    [info] [...] [main-chain] Answer: 2333333316666668
    ```

More details on the Project Euler's website: [https://projecteuler.net/overview=001](https://projecteuler.net/overview=001).

--8<-- "includes/license.md"
