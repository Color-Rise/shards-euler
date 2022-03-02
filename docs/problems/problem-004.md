# Problem 4: Largest palindrome product

Link to the problem: [https://projecteuler.net/problem=4](https://projecteuler.net/problem=4).

!!! quote "Problem 4"
    A palindromic number reads the same both ways. The largest palindrome made from the product of two 2-digit numbers is $9009 = 91 × 99$.

    Find the largest palindrome made from the product of two 3-digit numbers.

## A simple solution

Let our palindrom be $P = a \cdot b$.

$a$ and $b$ being 3-digit long, they must lie between $100$ and $999$.

Then once we have calculated the product we just need to compute the reverse number (i.e. where all digits are reversed)
and find that it is indeed the same number when a palindrome.

=== "Code"

    ```clojure linenums="1"
    --8<-- "src/problems/problem-004a.edn"
    ```


=== "Output"

    ```
    [info] [...] [main-chain] Answer: 906609
    ```

## A better solution

We can improve the previous implementation in two ways:
* halving the calculations
* counting downwards since we are looking for the largest palindrome

Halving the calculations comes from the fact that once we have checked for instance for $a = 123$ and $b = 456$,
we don't need to check again for $a = 456$ and $b = 123$. In other words, we could assume $a \leq b$.

Counting downwards means we start at $999$ instead of $100$ and we can stop once the product of $a \cdot b$ is less than the largest palindrome we found so far.

=== "Code"

    ```clojure linenums="1"
    --8<-- "src/problems/problem-004b.edn"
    ```


=== "Output"

    ```
    [info] [...] [main-chain] Answer: 906609    
    ```

## A much better solution

This is all good but we can improve even further. Let the digits of $P$ be $x$, $y$ and $z$.
Since $P$ is a palindrome, we have:

$$
\begin{align}
P & = 10^5x + 10^4y + 10^3z + 10^2z + 10y + x\\
  & = 100001x + 10010y + 1100z \\
  & = 11 (9091x + 910y + 100z)
\end{align}
$$

Since $11$ is prime, at least one of the numbers $a$ or $b$ must have a factor of $11$.
In other words if $a$ is not divisible by $11$ then we know $b$ necessarily must be.

=== "Code"

    ```clojure linenums="1"
    --8<-- "src/problems/problem-004c.edn"
    ```


=== "Output"

    ```
    
    ```

More details on the Project Euler's website: [https://projecteuler.net/overview=004](https://projecteuler.net/overview=004).

--8<-- "includes/license.md"
