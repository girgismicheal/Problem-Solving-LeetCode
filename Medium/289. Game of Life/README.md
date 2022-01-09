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
                
                if board[i][j] == 0 and ones_num==3:
                    board[i][j] = 'L'
                elif board[i][j] == 1:
                    if ones_num <=2:
                        board[i][j] = 'D'
                    elif ones_num <= 4:
                        board[i][j] = 1
                    else:
                        board[i][j] = 'D'
           
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

### Example 2:
> - board = [[1,1],[1,0]]
> - 



