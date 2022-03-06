# Problem 21: Amicable numbers

Link to the problem: [https://projecteuler.net/problem=21](https://projecteuler.net/problem=21).

!!! quote "Problem 21"
    Let $d(n)$ be defined as the sum of proper divisors of n (numbers less than n which divide evenly into n).

    If $d(a) = b$ and $d(b) = a$, where $a \neq b$, then a and b are an amicable pair and each of a and b are called amicable numbers.

    For example, the proper divisors of 220 are 1, 2, 4, 5, 10, 11, 20, 22, 44, 55 and 110; therefore $d(220) = 284$. The proper divisors of 284 are 1, 2, 4, 71 and 142; so $d(284) = 220$.

    Evaluate the sum of all the amicable numbers under 10000.

## A simple solution

=== "Code"

    ```clojure linenums="1"
    --8<-- "src/problems/problem-021a.edn"
    ```

=== "Output"

    ```
    [info] [...] [main-chain] Answer: 
    ```

More details on the Project Euler's website: [https://projecteuler.net/overview=021](https://projecteuler.net/overview=021).

--8<-- "includes/license.md"
