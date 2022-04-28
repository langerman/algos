# Stacks & Queues

## Stacks

Stacks are a last in first out (LIFO) data structure. To understand, what this means, we can think about stacks like a stack of plates. If you had a stack of plates and needed to access a specific plate, say one that was in the middle of the stack, the safest way to do so would be to continuously remove (i.e. stack.pop()) the top plate until the desired plated is reached. Similarly, the safest way to add a new plate to your stack of plates, would be to add the newest plate to the top of the stack (i.e. stack.push()). This is exactly how stacks operate as a data structure. Like our stack of plates, stacks add new elements and remove old elements from the top (i.e. in a last in first out fashion).

## Queues

Unlike stacks, queues are a first in first out (FIFO) data structure. The best way to understand queues is to think about them like standing in a line (or standing in "the queue"). If you arrive first, and are therefore ahead of someone else in line, you are serviced before them. Also like lines, queues add (queue.add()) to one end and remove (queue.remove()) from the other (i.e. you enter a line at the back of the line and are serviced and leave from the front of the line). Once you think about queues like lines, understanding how and when to use them becomes infinitely clearer.

## What to Know for Interviews

It’s good to know that stacks are particularly helpful during interview questions when you need to remember the occurrence of elements in reverse order or the last occurrence of something. For example, if you iterated through a string and pushed each character into a stack, you’d now have the same string stored in reverse order. Queues, on the other hand, can be very helpful when implementing a sliding window, or in other words, when you must process a sequence of elements but only consider N (your window size) elements a time. Using a queue allows you to, naturally, add new elements to the back of your queue and remove old, or expired, elements from the front of your queue. For example, if you were tasked to return whether or not an array has a subarray of size N that sums to a given target, this could be easily accomplished with a queue.
