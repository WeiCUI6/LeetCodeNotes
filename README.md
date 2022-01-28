# LeetCodeNotes
#### Description: Summary of what I have gained while practicing LeetCode. I would suggest memorize what I wrote down.

## LinkedList 
**Timeline (Jan. 24 - Jan. 28)**
1. Given the `head` of a linked list and an integer `val`, remove all the nodes of the linked list that has `Node.val == val`, and return the new `head` (L203).
    <p align="center">
        <img src="imgs/L203.png" width="48%"/>
    </p>
    
    * ```python
      class Solution:
          def removeElements(self, head, val):
              """
          :type head: ListNode
          :type val: int
          :rtype: ListNode
          """

          dummy_head = ListNode(-1)
          dummy_head.next = head

          current_node = dummy_head
          while current_node.next != None:
              if current_node.next.val == val:
                  current_node.next = current_node.next.next
              else:
                  current_node = current_node.next

          return dummy_head.next
    * It is enlightened to create a dummy node prefix to the given head node** and loop in that way.

2. Given the `head` of the linked list and get the middle node using fast and slow pointers. Remember the slow point always stops at index `n // 2`, (where n is the number of nodes in the linked list and index starts from 0)
    * ```python
      # The head node is given as input
      slow, fast = head, head
      # Get middle of linked list
	  while fast and fast.next:
		  fast = fast.next.next
		  slow = slow.next
      ```
3. Reverse linked list given the `head` node.
    * ```python
      curr, prev = head, None
      while curr:       
		    curr.next, prev, curr = prev, curr, curr.next
	
      # Return the head of reversed linked list
      return prev
      ```
      or 
    * ```python
      class Solution:
      # @param {ListNode} head
      # @return {ListNode}
      def reverseList(self, head):
          prev = None
          while head:
              curr = head
              head = head.next
              curr.next = prev
              prev = curr
          return prev
      ```
100. Some problems I didn't come up with a good idea when I first try to solve them. Maybe worth revisiting.
     * Easy: L1474, L705, L706, L716
     * Medium: L1265 (Important Follow-up Questions)
