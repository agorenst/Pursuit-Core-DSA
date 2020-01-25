```js
/**
 * @param {ListNode} l1
 * @param {ListNode} l2
 * @return {ListNode}
 */
var mergeTwoLists = function(l1, l2) {
    // We'll need to return the head of our list
    var resHead = null
    
    // We want to keep track of the node we want
    // to append to
    var resTail = null
    
    // Base cases:
    if (!l1 && !l2) { return null; }
    if (!l2) { return l1; }
    if (!l1) { return l2; }
    
    // Start up our result list
    // This is so we don't have to worry
    // about resHead/resTail being null
    // in the loop.
    if (l1.val < l2.val) {
        resHead = l1
        resTail = l1
        l1 = l1.next
    }
    else {
        resHead = l2
        resTail = l2
        l2 = l2.next
    }
    
    // Do the main loop iteration
    while (l1 && l2) {
        if (l1.val < l2.val) {
            resTail.next = l1
            l1 = l1.next
            //resTail = resTail.next
        }
        else {
            resTail.next = l2
            l2 = l2.next
            //resTail = resTail.next
        }
        // You may have wanted to put
        // the resTail = resTail.next in each if/else
        // branch, but we realize we can "sink" that
        // statement. Makes the nature of the loop clearer
        resTail = resTail.next
    }
    
    if (l1) {
        resTail.next = l1
    }
    if (l2) {
        resTail.next = l2
    }
    
    return resHead // the only time we use resHead...
};
```
