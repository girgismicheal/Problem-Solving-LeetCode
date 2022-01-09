# 289. Game of Life [Link](https://leetcode.com/problems/game-of-life/)
## Analysis of Algorithms
 - Time complexity: O(n*m)
 - Space complexity: O(1)


## The Code

```Python 
class Solution:
    def gameOfLife(self, board: List[List[int]]) -> None:
        """
        Do not return anything, modify board in-place instead.
        """
        def count_lives(row,col):
            # define the boundaries limits
            row_start = max(0,row-1)
            col_start = max(0 ,col-1)
            row_end = min(len(board),row+2)
            col_end = min(len(board[0]),col+2)
            #  Count the Ones or the dead ones in the kernel
            ones_num = 0
            for sublist in board[row_start:row_end]:
                for j in sublist[col_start:col_end]:
                    if (j==1) or (j=='D'):
                        ones_num+=1
            return ones_num
            
        # iterate over the matrix
        for i in range(len(board)):
            for j in range(len(board[0])):
                ones_num = count_lives(i,j) # Get the ones number
                # Rules definition
                # 'L' means 0 would be 1 at the next generation
                # 'D' means 1 would be 0 at the next generation
                if board[i][j] == 0 and ones_num==3: 
                    board[i][j] = 'L'
                elif board[i][j] == 1:
                    if ones_num <=2:
                        board[i][j] = 'D'
                    elif ones_num <= 4:
                        board[i][j] = 1
                    else:
                        board[i][j] = 'D'
        # transfer 'L' -> 1 and 'D' -> 0   
        for i in range(len(board)):
            for j in range(len(board[0])):
                if board[i][j] == 'L':
                    board[i][j] = 1
                elif board[i][j] == 'D':
                    board[i][j] = 0
```

## Examples
### Example 1:
> - board = [[0,1,0],[0,0,1],[1,1,1],[0,0,0]]
> - 
> - Kernel <br />
[0, 1] <br />
[0, 0]
> - Kernel
[0, 1, 0]<br />
[0, 0, 1]<br />

> - Kernel<br />
['D', 0]<br />
[0, 1]<br />

> - Kernel<br />
[0, 'D']<br />
[0, 0]<br />
[1, 1]<br />

> - Kernel<br />
[0, 'D', 0]<br />
['L', 0, 1]<br />
[1, 1, 1]<br />

> - Kernel<br />
['D', 0]<br />
[0, 1]<br />
[1, 1]<br />

> - Kernel
['L', 0]
[1, 1]
[0, 0]

> - Kernel
['L', 0, 1]
['D', 1, 1]
[0, 0, 0]

> - Kernel
[0, 1]
[1, 1]
[0, 0]

> - Kernel
['D', 1]
[0, 0]

> - Kernel
['D', 1, 1]
[0, 0, 0]

> - Kernel
[1, 1]
['L', 0]

### Example 2:
> - board = [[1,1],[1,0]]
> - 



