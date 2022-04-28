# Linked Lists

Linked lists are a linear collection in which the elements are not necessarily stored in contiguous memory locations. As a result of this, to maintain their relative order, each element in the list has a reference to the next element in the list. Each element in a list is typically referred to as a node and contains a specific type of object. While Java and other languages offer a linked list library, it’s very common during interviews to use custom node classes to store data as you please.

## What to Know for Interviews

Linked lists are a common topic during technical interviews questions, most of which involve traversing the list and returning a specific element, or modifying the list itself. Because of this, knowing how to traverse a linked list is paramount to being able to solve these questions. When traversing a linked list, the only reference you have to start is the head (or beginning) of the list. From the head you must continue traversing while you have not encountered a null node (i.e. the end of the list). Traversing the entirety of a linked list goes as follows:

    List<Integer> even = new ArrayList<>();
    // Store a reference to the start of the list in 'current'.
    ListNode current = head;
    while (current != null) {
        // Do something with current.
        if (current.val % 2 == 0) {
            even.add(current.val);
        }
        //Move current to the next element in the list using 'next'
        current = current.next;
    }
