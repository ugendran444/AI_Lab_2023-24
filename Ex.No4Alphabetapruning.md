# Ex.No: 4   Implementation of Alpha Beta Pruning 
### DATE: 23/09/2025                                                                          
### REGISTER NUMBER : 212222060283
### AIM: 
Write a Alpha beta pruning algorithm to find the optimal value of MAX Player from the given graph.
### Steps:
1. Start the program
2. Initially  assign MAX and MIN value as 1000 and -1000.
3.  Define the minimax function  using alpha beta pruning
4.  If maximum depth is reached then return the score value of leaf node. [depth taken as 3]
5.  In Max player turn, assign the alpha value by finding the maximum value by calling the minmax function recursively.
6.  In Min player turn, assign beta value by finding the minimum value by calling the minmax function recursively.
7.  Specify the score value of leaf nodes and Call the minimax function.
8.  Print the best value of Max player.
9.  Stop the program. 

### Program:
```
import math

def Alphabetapruning(depth, index, is_max, values, alpha, beta, targetDepth):
    # base case: targetDepth reached
    if depth == targetDepth:
        return values[index]

    func = max if is_max else min
    best = float('-inf') if is_max else float('inf')

    for i in range(2):  # iterate over the two possible child nodes
        val = Alphabetapruning(depth + 1, index * 2 + i, not is_max, values, alpha, beta, targetDepth)
        best = func(best, val)

        # Alpha-Beta Pruning
        if is_max:
            alpha = max(alpha, best)
        else:
            beta = min(beta, best)

        # Pruning: if beta <= alpha, break out of the loop
        if beta <= alpha:
            break

    return best

# Driver code
values = [3, 5, 6, 9, 1, 2, 0, -1]
targetDepth = math.ceil(math.log2(len(values)))  # calculate depth of the tree
print("The optimal value is:", Alphabetapruning(0, 0, True, values, float('-inf'), float('inf'),targetDepth))
```

### Output:
![Screenshot 2025-03-11 143750](https://github.com/user-attachments/assets/437ede73-d83c-431b-9d5b-afa06c9a8d12)

### Result:
Thus the best score of max player was found using Alpha Beta Pruning.
