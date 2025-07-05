## 2. Add Two Numbers

#### Python

```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution(object):
    def addTwoNumbers(self, l1, l2):
        """
        :type l1: ListNode
        :type l2: ListNode
        :rtype: ListNode
        """
        dummy_head = ListNode(0)
        current = dummy_head
        carry = 0
        
        while l1 is not None or l2 is not None or carry != 0:
            val1 = l1.val if l1 is not None else 0
            val2 = l2.val if l2 is not None else 0
            
            total = val1 + val2 + carry
            carry = total // 10
            digit = total % 10
            
            current.next = ListNode(digit)
            current = current.next
            
            if l1 is not None:
                l1 = l1.next
            if l2 is not None:
                l2 = l2.next
        
        return dummy_head.next
```

#### Go

```go
/**
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */
func addTwoNumbers(l1 *ListNode, l2 *ListNode) *ListNode {
    dummyHead := &ListNode{Val: 0}
    current := dummyHead
    carry := 0
    
    for l1 != nil || l2 != nil || carry != 0 {
        val1, val2 := 0, 0
        if l1 != nil {
            val1 = l1.Val
            l1 = l1.Next
        }
        if l2 != nil {
            val2 = l2.Val
            l2 = l2.Next
        }
        
        total := val1 + val2 + carry
        carry = total / 10
        digit := total % 10
        
        current.Next = &ListNode{Val: digit}
        current = current.Next
    }
    
    return dummyHead.Next
}
```

#### Rust

```rust
// Definition for singly-linked list.
// #[derive(PartialEq, Eq, Clone, Debug)]
// pub struct ListNode {
//   pub val: i32,
//   pub next: Option<Box<ListNode>>
// }
// 
// impl ListNode {
//   #[inline]
//   fn new(val: i32) -> Self {
//     ListNode {
//       next: None,
//       val
//     }
//   }
// }
impl Solution {
    pub fn add_two_numbers(l1: Option<Box<ListNode>>, l2: Option<Box<ListNode>>) -> Option<Box<ListNode>> {
        let mut dummy_head = Box::new(ListNode::new(0));
        let mut current = &mut dummy_head;
        let mut carry = 0;
        let mut p = l1;
        let mut q = l2;
        
        while p.is_some() || q.is_some() || carry != 0 {
            let val1 = p.as_ref().map_or(0, |node| node.val);
            let val2 = q.as_ref().map_or(0, |node| node.val);
            
            let total = val1 + val2 + carry;
            carry = total / 10;
            let digit = total % 10;
            
            current.next = Some(Box::new(ListNode::new(digit)));
            current = current.next.as_mut().unwrap();
            
            p = p.and_then(|node| node.next);
            q = q.and_then(|node| node.next);
        }
        
        dummy_head.next
    }
}
```