There are n bulbs and in every round the bulb at the ith position is toggled and we have to return the number of bulbs that are on after the nth round.

Assuming  n = 10
Round 1, turn on all bulbs so res = 10
Round 2, toggle every bulb at even postion so, res = 5
Round 3, toggle every bulb at every third index so, res = 6
Round 4, toggle every bulb at every fourth index so, res = 4
similarly calculating 
Round 5, res = 4
Round 6, res = 3
Round 7, res = 4
Round 8, res =5
Round 9, res =4
Round 10, res = 3

So by intuition we can say that the number of light bulbs on after n round of toggle will be floor(sqrt(n)).