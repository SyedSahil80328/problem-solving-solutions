# Problem Solving in LeetCode
In this repository, the solutions to some LeetCode problems in which some of them are optimal and others are close to optimal with explanations.

[LeetCode](https://leetcode.com/) is a popular platform for preparing for coding interviews and enhancing problem-solving skills. Key features include:

- **Extensive Problem Set**: Thousands of problems ranging from easy to hard, with detailed solutions and explanations.
- **Interview Preparation**: Dedicated sections for company-specific interview questions and interview simulation.
- **Discuss Forum**: A community forum where users can discuss problems, share solutions, and ask questions.
- **Contests**: Regular weekly and bi-weekly contests to challenge and compete with other programmers.

I like the thing from the LeetCode is that it let us to see the hidden testcase where our program gives wrong answer at no cost.

## Problem 2: [Add two numbers (Linked List)](https://leetcode.com/problems/add-two-numbers/description/):
This code defines a solution to the problem of adding two numbers represented as linked lists. The numbers are stored in reverse order, and each node contains a single digit. The goal is to add the two numbers and return the sum as a linked list.

### Explanation of the Approach

1. **Helper Functions**:
    - `insertNode(self, head, val)`: This function creates a new node with the given value (`val`) and inserts it at the beginning of the linked list, making it the new head. It returns the new head of the linked list.
    - `reverseList(self, head)`: This function reverses the linked list. It iterates through the list, reversing the direction of the links between the nodes. It returns the new head of the reversed list.

2. **Main Function**:
    - `addTwoNumbers(self, l1, l2)`: This is the main function that adds two numbers represented by the linked lists `l1` and `l2`.

3. **Algorithm**:
    - **Initialization**: 
        - `temp1` and `temp2` are initialized to `l1` and `l2`, respectively, to traverse the linked lists.
        - `head` is initialized to `None`, which will be used to build the result linked list.
        - `carry` is initialized to `0` to handle the carry-over during the addition.

    - **First Loop (Simultaneous Traversal)**:
        - The function iterates through both linked lists simultaneously as long as both have nodes.
        - It calculates the sum of the current nodes' values and the carry from the previous addition.
        - If the sum is greater than 9, it sets `carry` to 1 and updates the value to be the remainder when divided by 10.
        - It inserts the resulting value at the beginning of the result linked list using `insertNode`.

    - **Second Loop (Remaining Nodes in l1)**:
        - If `l1` has remaining nodes after `l2` is exhausted, this loop processes the remaining nodes.
        - It adds the carry to each node's value, updates the carry if necessary, and inserts the resulting value at the beginning of the result linked list.

    - **Third Loop (Remaining Nodes in l2)**:
        - If `l2` has remaining nodes after `l1` is exhausted, this loop processes the remaining nodes.
        - Similar to the second loop, it adds the carry to each node's value, updates the carry if necessary, and inserts the resulting value at the beginning of the result linked list.

    - **Final Carry Check**:
        - If there is a remaining carry after processing all nodes, it inserts a new node with value `1` at the beginning of the result linked list.

    - **Reversing the Result**:
        - Since the result linked list is built in reverse order, it is reversed using the `reverseList` function to restore the correct order.

4. **Return**:
    - The function returns the head of the reversed result linked list, which represents the sum of the two numbers.

This approach ensures that the addition is handled correctly, including the carry, and builds the result linked list efficiently.

## Problem 21: [Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists):
This code defines a solution to merge two sorted linked lists into one sorted linked list. The merging is done by comparing the values of the nodes in both lists and inserting the smaller value into the new list. Here's a detailed explanation of the approach:

### Explanation of the Approach

1. **Helper Functions**:
    - `insertNode(self, head, value)`: This function creates a new node with the given value (`value`) and inserts it at the beginning of the linked list, making it the new head. It returns the new head of the linked list.
    - `reverseList(self, head)`: This function reverses the linked list. It iterates through the list, reversing the direction of the links between the nodes. It returns the new head of the reversed list.

2. **Main Function**:
    - `mergeTwoLists(self, list1, list2)`: This is the main function that merges two sorted linked lists `list1` and `list2`.

3. **Algorithm**:
    - **Initialization**:
        - `temp1` and `temp2` are initialized to `list1` and `list2`, respectively, to traverse the linked lists.
        - `head` is initialized to `None`, which will be used to build the result linked list.

    - **First Loop (Simultaneous Traversal)**:
        - The function iterates through both linked lists simultaneously as long as both have nodes.
        - It compares the values of the current nodes of both lists.
        - It inserts the smaller value at the beginning of the result linked list using `insertNode`.
        - It moves to the next node in the list from which the smaller value was taken.

    - **Second Loop (Remaining Nodes in list1)**:
        - If `list1` has remaining nodes after `list2` is exhausted, this loop processes the remaining nodes.
        - It inserts each remaining value at the beginning of the result linked list using `insertNode`.

    - **Third Loop (Remaining Nodes in list2)**:
        - If `list2` has remaining nodes after `list1` is exhausted, this loop processes the remaining nodes.
        - It inserts each remaining value at the beginning of the result linked list using `insertNode`.

    - **Reversing the Result**:
        - Since the result linked list is built in reverse order, it is reversed using the `reverseList` function to restore the correct order.

4. **Return**:
    - The function returns the head of the reversed result linked list, which represents the merged sorted list.

This approach ensures that the two sorted linked lists are merged correctly into one sorted linked list by comparing the values and inserting them in the correct order. The final list is reversed to achieve the correct order since the nodes were inserted at the beginning during the merging process.
