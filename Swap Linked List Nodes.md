# Intuition

We know from the hint that it will be very complicated to swap nodes in a linked list so we use an array to first store the values and after swapping, we construct another Linked List.

  

# Approach

First we use a while loop to deconstruct the Linked list and push the values in an array, then we swap the values in the Array (take note that the k given is not an index but a position so choose the indexes accordingly), then using a for loop on the array we construct a Linked List we store the head of the linked list in a extra variabcle. Then return the head.

  

# Code

```

/**

* Definition for singly-linked list.

* class ListNode {

* val: number

* next: ListNode | null

* constructor(val?: number, next?: ListNode | null) {

* this.val = (val===undefined ? 0 : val)

* this.next = (next===undefined ? null : next)

* }

* }

*/

  

function swapNodes(head: ListNode | null, k: number): ListNode | null {

const tempArr:number[]=[];

let tempNode:ListNode= head;

while(tempNode!==null){

tempArr.push(tempNode.val);

tempNode=tempNode.next;

}

const len:number=tempArr.length;

const val1:number=tempArr[k-1];

tempArr[k-1]=tempArr[len-k];

tempArr[len-k]=val1;

let resNode:ListNode = new ListNode(tempArr[0]);

let resNode2:ListNode=resNode;

for(var i:number=1;i<len;i++){

tempNode = new ListNode(tempArr[i]);

resNode.next = tempNode;

resNode=resNode.next;

}

return resNode2;

};

```