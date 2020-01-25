# Print a Linked List Recursively Solution

## Javascript

```js
/**
 * Definition for singly-linked list.
function ListNode(val) {
    this.val = val;
    this.next = null;
}
 */
```

```js
function PrintLinkedList(l) {
    // Easy case: if l is null, then there's nothing to print!
    
    if (!l) { return; }
    
    console.log(l.val)

    PrintLinkedList(l.next)
}
```

Let's test our code to be sure. What are some interesting test cases?
```js
var emptyList = null
console.log("Printing the empty list, should have nothing after this line:")
PrintLinkedList(emptyList)
console.log("Here's hoping.")

var sizeOneList = new ListNode(1)
console.log("Printing size-one list, expecting '1'")
PrintLinkedList(sizeOneList)

var sizeTwoList = new ListNode(2)
// Here's an interesting fact, how we can stitch together linked lists
// to make big ones. Just don't get tangled...
sizeTwoList.next = sizeOneList
console.log("Printing size-two list")
PrintLinkedList(sizeTwoList)

// And I think that's enough.
```
