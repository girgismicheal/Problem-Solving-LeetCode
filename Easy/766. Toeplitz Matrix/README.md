# 766. Toeplitz Matrix [Link](https://leetcode.com/problems/toeplitz-matrix/)

## Analysis of Algorithms
 - Time complexity: O(n)
 - Space complexity: O(1)

## The Code

```Python
class Solution:
    def isToeplitzMatrix(self, matrix: List[List[int]]) -> bool:
        
        dia = {}
        for i in range(len(matrix[0])):
            dia[i] = matrix[0][i]
        for i in range(len(matrix)):
            dia[-i] = matrix[i][0]

        for i in range(len(matrix)):
            for j in range(len(matrix[0])):
                if dia[-i+j] != matrix[i][j]:
                    return False
        return True
```

## Examples

### Example 1:

### Example 2:

### Example 3:


