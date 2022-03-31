[Welcome Page](https://github.com/Morthais/data_structure_final/blob/main/0-welcome.md)

# Stack

## Introduction

### What is a stack? 

Imagine you are building a pile of bricks. A pile of bricks is built by placing one brick on top of another until you run out of bricks to put on the pile. If you want to get to the bricks at the bottom, you need first to take from the top. You can do other things like count the bricks and verify that you have the right amount, but that doesn't change the fact that the last brick you put on the pile is the first one you take off. We call this rule the Last In First Out (LIFO) structure and it is key to understanding stacks. A stack is essentially a pile of bricks. When we put a brick on top of the stack we call it a push. When we take a brick off the top of the stack we call it a pop. You can do other things like check the size of the stack and verify that number is correct, but anything lower in the stack is not accessible until the items above it have been removed first.

![Stack_Bricks](https://user-images.githubusercontent.com/60240900/159603777-fec80413-e7cc-4520-b175-f827365ad152.png)

### What is the purpose of a stack? 

Every data structure is a tool that is better at solving some problems than others. A stack is really good at remembering where we have been. There are many uses for retaining a history, but one of the most important is the function stack. [The Function Stack](https://developer.mozilla.org/en-US/docs/Glossary/Call_Stack) is a good example of a stack implemented in programs every day and is good to understand as you move forward to develop more complex software.

### What kind of errors are common when using a stack?

Common errors when using a stack are any errors common to the Python List.

Index Error

![Index Error](https://user-images.githubusercontent.com/60240900/160949510-162fd322-01c9-4c62-8de1-77fade07a8eb.png)

Name Error

![Name Error](https://user-images.githubusercontent.com/60240900/160949706-4eb86a59-4a4b-48a2-bfd2-fc77d2f228bf.png)

Attribute Error

![Attribute Error](https://user-images.githubusercontent.com/60240900/160949891-12c1d36a-5b77-4b95-9642-7d875f40f92c.png)

Indentation Error

![Indentation Error](https://user-images.githubusercontent.com/60240900/160950017-478a1f9c-33d8-4767-b0a1-6ce853e2d9a3.png)

## Stack Functions in Python

When considering a data structure it is important to know the performance of that data structure. As you learn the functions used by stacks, consider how efficient the stack operation is by reading it's Big O Notation. Basically, the Big O Notation of an operation is how fast it is. About halfway down [THIS](https://jarednielsen.com/big-o-notation/) article you will see a table explaining the most important notations to know and their speeds. I recommend reading the whole article to get a good handle of the basics of Big O Notation. It will become increasingly important going forward.

|Function|Python Code|Description|Performance|
|---|---|---|---|
|insert()|stack_list.append(item)|Add an 'item' to the top of a stack.|O(1), Constant Time performance for adding to the top of a stack.|
|remove()|item = stack_list.pop()|Remove and return an 'item' from the top of a stack.|O(1), Constant Time performance for removing from the top of a stack.|
|is_empty()|if len(stack_list) <= 0:|Returns True if stack is empty, False if stack is not empty.|O(1), Constant Time performance for checking the length of a stack.|
|check_top()|print(stack_list[-1])|Show the last item in the stack.|O(1), Constant Time performance for printing an item from a stack.|
|check_size()|print(len(stack_list))|Return and show the length of a stack.|O(1), Constant Time performance for checking the length of a stack.|

## Example

How would a stack be used in Python? Remember, a stack is basically just a list that follows the Last In First Out rules. Copy the example below into your code editor and run it to better understand how stacks work.

```
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

## Problem

Now it's your turn! Reverse the three following sentences using stacks in Python.

1. ".gnitseretni efil sekam taht eurt emoc maerd a gnivah fo ytilibissop eht s'tI"
2. ".ssendlob ,namow gnuoy a ni ,ytidimit si nam a ni evol eurt fo motpmys tsrif ehT"
3. ".eveileb uoy tahw rof gnireffus dna gnivil ni si egaruoc laer ehT .nommoc etiuq yllautca s'ti ;sfeileb rieht rof deid evah elpoep ynam taht dnim ni peeK"

HINT: Reversing a sentence may require using more than one stack.

```
"""
One way to reverse a sentence in Python using stacks.
"""

def reverse_sentence(original_sentence, reverse_stack, result):
    # TODO: add any code necessary here
    pass

    
# The three sentences to reverse
sentence_1 = ".gnitseretni efil sekam taht eurt emoc maerd a gnivah fo ytilibissop eht s'tI"
sentence_2 = ".ssendlob ,namow gnuoy a ni ,ytidimit si nam a ni evol eurt fo motpmys tsrif ehT"
sentence_3 = ".eveileb uoy tahw rof gnireffus dna gnivil ni si egaruoc laer ehT .nommoc etiuq yllautca s'ti ;sfeileb rieht rof deid evah elpoep ynam taht dnim ni peeK"

# TODO: add any additional variables required to reverse a sentence using stacks

# Reverse the first sentence

reverse_sentence(original_sentence, reverse_stack, result)

# Reverse the second sentence

reverse_sentence(original_sentence, reverse_stack, result)

# Reverse the third sentence

reverse_sentence(original_sentence, reverse_stack, result)
```

## Explore a Python Module

The first link is to a Python stack module from the built-in Python queue class. The second link is on the same page and shows what methods/functions are available to you in this module. It includes a put, get, empty, and size among others. This is optional learning and may or may not help you with the problem above.

[Python queue.LifoQueue](https://docs.python.org/3/library/queue.html#queue.LifoQueue)

[Python queue.Queue Methods](https://docs.python.org/3/library/queue.html#queue-objects)

## References

[Reverse Sentence Solution](https://github.com/Morthais/data_structure_final/blob/main/1-stack_solution.md)

[Error Types in Python](https://www.tutorialsteacher.com/python/error-types-in-python)

[Extra Help with Stacks](https://realpython.com/how-to-implement-python-stack/)
