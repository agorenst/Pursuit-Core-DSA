# Count a Linked List Solutions

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
function CountLinkedListRecursively(l) {
    // Easy case: if l is null, then there's nothing to print!
    
    if (!l) { return 0; }
    
    var suffix = l.next
    var suffixLength = CountLinkedListRecursively(suffix)
    
    var myLength = 1 + suffixLength
    
    return suffixLength
}
```

```js
function CountLinkedListIteratively(l) {
    // Easy case: if l is null, then there's nothing to print!
    
    var c = 0
    var n = l
    while (n) {
        c += 1
        n = n.next
    }
    
    return c
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
