In this question we have to choose from an array of questions where each element of the array contains an array with two elements where the first element is the points you get by solving the question and the second element is the no of brainpower used, so we won't be able to answer the next n questions.

We have to find the maximum points we can score by answer the questions, we can used dynamic programming to store the number of points scored if we decide to start at a particular question.

If we solve a question we can't solve the next n questions and we will get points of the questions. If we skip on a question the points remain the same and we can solve the next question. 

We only need a 1D array to keep track of the points we get and we start from the last question and then go back from there checking every question that is not skipped if we answer the ith question. And if the points are greater than the previous question we update the points for that index meaning that we attempt the question, else we just take the preious maximum and store it meaning that we skip the question.


```
function mostPoints(questions: number[][]): number {
    const len:number = questions.length;
    const dp:number[]= Array(len).fill(0);
    dp[len-1]=questions[len-1][0];
    for(let i:number=len-2;i>=0;i--){
        const [points,brainpower]=questions[i];
        const unskipped:number = i+brainpower+1;
        if(unskipped>=len){
            dp[i]=points;
        }else{
            dp[i]=points+dp[unskipped];
        }
        dp[i]=Math.max(dp[i],dp[i+1]);
    }
    return dp[0];
};
```