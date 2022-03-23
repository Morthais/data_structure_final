# Stack

[Welcome Page](https://github.com/Morthais/data_structure_final/blob/main/0-welcome.md)

## Introduction

### What is a stack? 

Imagine you are building a pile of bricks. A pile of bricks is built by placing one brick on top of another until you run out of bricks to put on the pile. If you want to get to the bricks at the bottom, you need first to take from the top. You can do other things like count the bricks and verify that you have the right amount, but that doesn't change the fact that the last brick you put on the pile is the first one you take off. We call this rule the Last In First Out (LIFO) structure and it is key to understanding stacks. A stack is essentially a pile of bricks. When we put a brick on top of the stack we call it a push. When we take a brick off the top of the stack we call it a pop. You can do other things like check the size of the stack and verify that number is correct, but anything lower in the stack is not accessible until the items above it have been removed first.

![Stack_Bricks](https://user-images.githubusercontent.com/60240900/159603777-fec80413-e7cc-4520-b175-f827365ad152.png)

### What is the purpose of a stack? 

Every data structure is a tool that is better at solving some problems than others. A stack is really good at remembering where we have been. There are many uses for retaining a history, but one of the most important is the function stack. [The Function Stack]() is a good example of a stack implemented in programs every day and is good to understand as you move forward to develop more complex software.

### What kind of errors are common when using a stack?

TBD

## Stack Functions/Methods in Python

What is the performance of a stack? NOTE: This should probably be answered in the functions section, showing the Big O Notation of each function.

|Function|Python Code|Description|Performance|
|---|---|---|---|
|insert()|stack_list.append(item)|Add an 'item' to the top of a stack.|O(1), Constant Time performance for adding to the top of a stack.|
|remove()|item = stack_list.pop()|Remove and return an 'item' from the top of a stack.|O(1), Constant Time performance for removing from the top of a stack.|
|is_empty()|if len(stack_list) <= 0:|Returns True if stack is empty, False if stack is not empty.|O(1), Constant Time performance for checking the length of a stack.|
|check_top()|print(stack_list[-1])|Show the last item in the stack.|O(1), Constant Time performance for printing an item from a stack.|
|check_size()|print(len(stack_list))|Return and show the length of a stack.|O(1), Constant Time performance for checking the length of a stack.|

## Example 1

How would a stack be used in Python? In Python, a stack is basically just a list that follows the Last In First Out rules. NOTE: Show Example

TBD

## Example 2

How would a stack be used in Python? In Python, a stack is basically just a list that follows the Last In First Out rules. NOTE: Show Example

TBD

## Problem

TBD

## Helpful Python Module

TBD

## References

TBD
