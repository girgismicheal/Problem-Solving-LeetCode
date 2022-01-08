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
> - matrix = [[1,2,3,4],[5,1,2,3],[9,5,1,2]]
> - dia = {0: 1, 1: 2, 2: 3, 3: 4}
> - dia = {0: 1, 1: 2, 2: 3, 3: 4, -1: 5, -2: 9}
> - i = 0 j= 0 : dia[ 0 ]= 1 and matrix[ 0 ][ 0 ] =  1
> - i = 0 j= 1 : dia[ 1 ]= 2 and matrix[ 0 ][ 1 ] =  2
> - i = 0 j= 2 : dia[ 2 ]= 3 and matrix[ 0 ][ 2 ] =  3
> - i = 0 j= 3 : dia[ 3 ]= 4 and matrix[ 0 ][ 3 ] =  4
> - i = 1 j= 0 : dia[ -1 ]= 5 and matrix[ 1 ][ 0 ] =  5
> - i = 1 j= 1 : dia[ 0 ]= 1 and matrix[ 1 ][ 1 ] =  1
> - i = 1 j= 2 : dia[ 1 ]= 2 and matrix[ 1 ][ 2 ] =  2
> - i = 1 j= 3 : dia[ 2 ]= 3 and matrix[ 1 ][ 3 ] =  3
> - i = 2 j= 0 : dia[ -2 ]= 9 and matrix[ 2 ][ 0 ] =  9
> - i = 2 j= 1 : dia[ -1 ]= 5 and matrix[ 2 ][ 1 ] =  5
> - i = 2 j= 2 : dia[ 0 ]= 1 and matrix[ 2 ][ 2 ] =  1
> - i = 2 j= 3 : dia[ 1 ]= 2 and matrix[ 2 ][ 3 ] =  2
> - True


### Example 2:
> - matrix = [[1,2],[2,2]]
> 



