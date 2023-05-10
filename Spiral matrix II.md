For a given n generate a n x n matrix that has elements filled in a spiral manner
![[Pasted image 20230510135329.png]]
if n=3,
then return, \[[1,2,3],[8,9,4],[7,6,5]\]

So we have to add elements at the indexes (0,0),(0,1),(0,2),(1,2),(2,2),(2,1),(2,0),(1,0),(1,1)

The intuition is same as the first spiral matrix problem but we just update the array elements.
```
/**
 * @param {number} n
 * @return {number[][]}
 */
var generateMatrix = function(n) {
    if(n==1){return [[1]]}
    const res = new Array(n).fill().map(()=>Array(n).fill(0));
    console.log(res);
    var direction = 0;
    var left =0;
    var right=n-1;
    var bottom=n-1;
    var top=0;
    var i=1;
    while(i<=n*n){
        if(direction==0){
            for(var j=left;j<=right;j++){
                res[top][j]=i;
                i++;
            }
            top++;
            direction++;
        }else if(direction==1){
            for(var j=top;j<=bottom;j++){
                res[j][right]=i;
                i++;
            }
            right--;
            direction++;
        }else if(direction==2){
            for(var j=right;j>=left;j--){
                res[bottom][j]=i;
                i++;
            }
            bottom--;
            direction++;
        }else if(direction==3){
            for(var j=bottom;j>=top;j--){
                res[j][left]=i;
                i++;
            }
            left++;
            direction++;
        }else if(direction==4){
            direction=0;
        }
    }
    return res;
};
```