![[Pasted image 20230509125040.png]]

## Return an array of elements of the matrix in a spiral manner
###  [1,2,3,6,9,8,7,4,5]
So now looking at the indices of the matrix in spiral order
###   \[[0,0],[0,1],[0,2],[1,2],[2,2],[2,1],[2,0],[1,0],[1,1]]

We will have 4 directions to move in right,down,left,up and we will need 4 limits right,down,left,up, so we can give each direction a code from 0 to 3 and 4th one for resetting the direction to 0.

We use a while loop till there are m\*n elements in our result array.

Then we move right till the right limit number,whose direction code is 0 and push elements into the result array.
Then we update the right limit to right--

Then increment the direction to start moving in the down direction and in this way we can keep switching directions till the matrix in fully traversed.

```/**
 * @param {number[][]} matrix
 * @return {number[]}
 */
var spiralOrder = function(matrix) {
    let arr = []
    let r = matrix.length;
    let c = matrix[0].length;
    let direction = 0;
    let left = 0;
    let right = c-1;
    let bottom = 0;
    let top = r-1;

    while(arr.length<r*c){
        if(direction == 0){
            for(let i = left; i<=right; i++){
                arr.push(matrix[bottom][i])
            }
            bottom++
            direction++
        }
        else if(direction == 1){
            for(let i = bottom; i<=top; i++){
                arr.push(matrix[i][right])
            }
            right--
            direction++
        }
        else if(direction == 2){
            for(let i = right; i>=left;i--){
                arr.push(matrix[top][i])
            }
            top--
            direction++
        }
        else if(direction==3){
            for(let i =top; i>=bottom; i--){
                arr.push(matrix[i][left])
            }
            left++
            direction++
        }
        if(direction == 4) direction = 0;
    }
    return arr;
};
```
