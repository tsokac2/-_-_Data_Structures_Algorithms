<h1 align="center">Coding Challenges</h1>

#
### Create Rectangles

Given a rectangle with dimensions N*M and an integer K. You divide this rectangle into smaller sub-rectangles such that the given conditions are satisfied:

- Sub-rectangles must be parallel to the axis of the large rectangle with dimensions N*M.
- Every sub-rectangle has at least one edge on the large rectangle edge. Informally, there is no sub-rectangle that is surrounded by other sub-rectangles.

For a sub-rectangle with an area S, the cost of this sub-rectangle is (S - K)^2.

Calculate the minimum total cost to divide the large rectangle into smaller sub-rectangles.

Note: All sub-rectangles must have an integral length of dimensions.

#### Function description

Complete the `solve` function. This function takes the following 3 parameters and returns the required answer:

- `N`: Represents the value of `N`
- `M`: Represents the value of `M`
- `K`: Represents the value of `K`

#### Input format for custom testing

**Note:** Use this input format if you are testing against custom input or writing code in a language where we don't provide boilerplate code.
- The first line contains `T`, which represents the number of test cases.
- For each test case:
    - The first line contains an integer `N`.
    - The second line contains an integer `M`.
    - The third line contains an integer `K`.

#### Output format
For each test case in a new line, print the answer representing the minimum cost.

