---
title: "Codility Lesson6: MaxProductOfThree"
categories:
  - Coding challenge
tags:
  - Codility
header:
  teaser: /assets/images/codility.png
  overlay_image: /assets/images/codility.png
  overlay_filter: 0.4
sidebar:
  nav: "coding"
author_profile: false
---

Sharing an answer code of mine about [MaxProductOfThree problem of Codility lesson 6](https://app.codility.com/programmers/lessons/6-sorting/max_product_of_three/start/).

{% include toc title="Table of Contents" icon="file-text" %}

# Lesson 6: MaxProductOfThree
A non-empty zero-indexed array A consisting of N integers is given. The product of triplet (P, Q, R) equates to A[P] * A[Q] * A[R] (0 ≤ P < Q < R < N).

For example, array A such that:

$$
  A[0] = -3\\
  A[1] = 1\\
  A[2] = 2\\
  A[3] = -2\\
  A[4] = 5\\
  A[5] = 6\\
$$

contains the following example triplets:

- (0, 1, 2), product is −3 * 1 * 2 = −6
- (1, 2, 4), product is 1 * 2 * 5 = 10
- (2, 4, 5), product is 2 * 5 * 6 = 60

Your goal is to find the maximal product of any triplet.

Write a function:

```python
def solution(A)
```

that, given a non-empty zero-indexed array A, returns the value of the maximal product of any triplet.

For example, given array A such that:

$$
  A[0] = -3\\
  A[1] = 1\\
  A[2] = 2\\
  A[3] = -2\\
  A[4] = 5\\
  A[5] = 6\\
$$

the function should return 60, as the product of triplet (2, 4, 5) is maximal.

Assume that:

- N is an integer within the range [3..100,000];
- each element of array A is an integer within the range [−1,000..1,000].

Complexity:

- expected worst-case time complexity is O(N*log(N));
- expected worst-case space complexity is O(1), beyond input storage (not counting the storage required for input arguments).

# Answer Code in Python 3

- Time complexity: $$O(N\log N)$$

```python
# Time complexity: O(N*log(N))
# you can write to stdout for debugging purposes, e.g.
# print("this is a debug message")
import math

def solution(A):
    # write your code in Python 3.6
    max = -math.inf
    A.sort()
    for i in range(0, -4, -1):
        if max < A[0 + i] * A[1 + i] * A[2 + i]:
            max = A[0 + i] * A[1 + i] * A[2 + i]

    return max
```
