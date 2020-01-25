# Print a Linked List Solution

## Javascript

Here's how we define our linked list class, from leetcode.
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
    
    // Here's the interesting part: we need to iterate through
    // the list. Just like how iterating through an array, you have
    // and index "i" and think about "a[i]" (without ever actually
    // changing the array, a), we'll have an iterator "n" that is
    // always a reference to our current node we want to print.
    
    var n = l
    while (n) {
        // Print the value of n
        console.log(n.val)

        // Now we want n to be changed so it refers
        // to the following node.
        n = n.next
    }
    
    // That's it! The above simple loop is the right building block
    // for iterating through a linked-list.
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
