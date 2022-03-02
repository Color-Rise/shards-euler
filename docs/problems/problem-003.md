# Problem 3: Largest prime factor

Link to the problem: [https://projecteuler.net/problem=3](https://projecteuler.net/problem=3).

!!! quote "Problem 3"
    The prime factors of 13195 are 5, 7, 13 and 29.

    What is the largest prime factor of the number 600851475143 ?

## A simple solution

Here we basically try every $k = 2,3,4,5,...$ and if it is a factor of $n$, we divide $n$ by $k$ as many times as necessary until $k$ is no longer a multiple. Then we moved to the next $k$.

=== "Code"

    ```clojure linenums="1"
    --8<-- "src/problems/problem-003a.edn"
    ```


=== "Output"

    ```
    [info] [...] [main-chain] Answer: 4613732
    ```

## A slightly better solution

$2$ is the only even prime, so if we check $2$ separately first, we can increase $k$ each step by $2$,
avoiding unnecessary checks that would always fail for all even factors.

=== "Code"

    ```clojure linenums="1"
    --8<-- "src/problems/problem-003b.edn"
    ```

=== "Output"

    ```
    [info] [...] [main-chain] Answer: 4613732
    ```

## A much better solution

Suppose now that the number to test is much larger (e.g. $4287721622247962$) and with a big prime as a factor. It could take quite a while to reach that big prime.

This can be simplified with the realisation that at most one prime factor can be greater than $\sqrt{n}$. In other words, after finding one factor for the remaining number $n$ we can use $\sqrt{n}$ as the upper limit for $k$.

=== "Code"

    ```clojure linenums="1"
    --8<-- "src/problems/problem-003c.edn"
    ```

=== "Output"

    ```
    [info] [...] [main-chain] n: 4287721622247962
    [info] [...] [main-chain] Answer: 5829843479
    ```

More details on the Project Euler's website: [https://projecteuler.net/overview=003](https://projecteuler.net/overview=003).

--8<-- "includes/license.md"
