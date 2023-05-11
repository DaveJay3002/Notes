![[Pasted image 20230511102127.png]]
We have to return the number of uncrossed lines by connecting the same numbers in the two arrays, in the example above we return two.

### Intuition
We can use Dynamic Programming to keep a track of the uncrossed lines, in a 2 dimensional array of size len1+1 and len2+1

```
function maxUncrossedLines(nums1: number[], nums2: number[]): number {

let len1:number=nums1.length;

let len2:number=nums2.length;

let res:number=0;

let dp:number[][]=Array(len1+1).fill(null).map(()=>Array(len2+1).fill(0));

for(let i:number=0;i<len1;i++){

for(let j:number=0;j<len2;j++){

if(nums1[i]===nums2[j]){

dp[i+1][j+1]=dp[i][j]+1;

}else{

dp[i+1][j+1]=Math.max(dp[i+1][j],dp[i][j+1]);

}

}

}

// console.log(dp);

return dp[len1][len2];

};
```

If the the index of the numbers matches we increment the number in our dp matrix else we take the max of the upper or side index from the matrix, in this way the final index of the matrix dp\[len1\]\[len2\]  is the number of uncrossed lines.