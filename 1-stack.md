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

```
"""
Example of how to push and pop from a stack of bricks in Python.
"""
import time

def push_stack(stack_of_bricks):
    # create 5 bricks
    for brick in range(1, 6):
        time.sleep(1)   # wait 1 second
        stack_of_bricks.append(f"Brick {brick}")    # put a brick on the stack
        print(f"Pushed {stack_of_bricks[brick - 1]} to the stack: {stack_of_bricks}")     # show the updated stack
    
    return stack_of_bricks


def pop_stack(stack_of_bricks):
    # go through all 5 bricks
    for brick in range(1, 6):
        time.sleep(1)   # wait 1 second
        removed_brick = stack_of_bricks.pop()   # remove a brick from the stack
        print(f"Popped {removed_brick} from the stack: {stack_of_bricks}")     # show the updated stack


# the stack
stack_of_bricks = []

print("\nNow pushing to the stack . . . . .")
stack_of_bricks = push_stack(stack_of_bricks)
print()

print("Now popping off the stack . . . . .")
pop_stack(stack_of_bricks)
print()
```

## Example 2

How would a stack be used in Python? In Python, a stack is basically just a list that follows the Last In First Out rules. NOTE: Show Example

```
"""
Example of how to reverse a sentence in Python using stacks.
"""

original_stack = list("It is possible to commit no mistakes and still lose. That is not weakness, that is life. ― Jean-Luc Picard")
reversed_stack = []
reversed_sentence = ""

def reverse_sentence(reversed_sentence):
    # reverse the sentence using a stack
    for char in range(len(original_stack)):
        last_char = original_stack.pop()
        reversed_stack.append(last_char)

    # build the reversed sentence string from the reversed stack
    for char in range(len(reversed_stack)):
        reversed_sentence = reversed_sentence + reversed_stack[char]

    print(reversed_sentence)

reverse_sentence(reversed_sentence)
```

## Problem

Reverse three sentences using one stack:

"For the first time, he heard something that he knew to be music. He heard people singing. Behind him, across vast distances of space and time, from the place he had left, he thought he heard music too. But perhaps, it was only an echo. ― Lois Lowry, quote from The Giver"

"When you teach them-teach them not to fear. Fear is good in small amounts, but when it is a constant, pounding companion, it cuts away at who you are and makes it hard to do what you know is right. ― Christopher Paolini, Inheritance"

"It's the possibility of having a dream come true that makes life interesting. ― Paulo Coelho, The Alchemist"

## Helpful Python Module

TBD

## References

TBD
