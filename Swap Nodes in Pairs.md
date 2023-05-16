![[Pasted image 20230516122921.png]]

Here we are given a Linked List and we have to swap the adjacent nodes and return the linked list but we can't change the values of the nodes.

First we use a while loop to deconstruct the Linked list and push the values in an array, then we swap the values in the Array and then create a new Linked List and return it's head.

```
function swapPairs(head: ListNode | null): ListNode | null {

let tempNode:ListNode=head;

const temparr:number[]=[];

while(tempNode!=null){

temparr.push(tempNode.val);

tempNode=tempNode.next;

}

if(temparr.length===0 || temparr.length===1) return head;

for(var i:number=0;i<temparr.length-1;i=i+2){

let temp = temparr[i];

temparr[i]=temparr[i+1];

temparr[i+1]=temp;

}

tempNode= new ListNode(temparr[0]);

let resNode:ListNode =tempNode;

for(var i:number=1;i<temparr.length;i++){

let newNode:ListNode= new ListNode(temparr[i]);

tempNode.next = newNode;

tempNode = tempNode.next;

}

return resNode;

};
```


