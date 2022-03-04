# Problem 14: Longest Collatz sequence

Link to the problem: [https://projecteuler.net/problem=14](https://projecteuler.net/problem=14).

!!! quote "Problem 14"

    The following iterative sequence is defined for the set of positive integers:

    $$
    n \to
    \begin{cases}
    n/2,  & \text{if $n$ is even} \\
    3n+1, & \text{if $n$ is odd}
    \end{cases}
    $$

    Using the rule above and starting with 13, we generate the following sequence:

    $$
    13 \to 40 \to 20 \to 10 \to 5 \to 16 \to 8 \to 4 \to 2 \to 1
    $$

    It can be seen that this sequence (starting at 13 and finishing at 1) contains 10 terms. Although it has not been proved yet (Collatz Problem), it is thought that all starting numbers finish at 1.

    Which starting number, under one million, produces the longest chain?

    **NOTE:** Once the chain starts the terms are allowed to go above one million.

## A simple solution

=== "Code"

    ```clojure linenums="1"
    --8<-- "src/problems/problem-014a.edn"
    ```

=== "Output"

    ```
    [info] [...] [main-chain] Answer: 
    ```

More details on the Project Euler's website: [https://projecteuler.net/overview=014](https://projecteuler.net/overview=014).

--8<-- "includes/license.md"
