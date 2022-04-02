# Tree

[Welcome Page](https://github.com/Morthais/data_structure_final/blob/main/0-welcome.md)

## Introduction

### What is a tree?

Imagine your biological family history. If you are like most people then you have one mother and one father. Following this pattern, each of your parents also has a mother and a father (you call these your grandparents). Yet further, even back to the beginning of time, every person has one biological mother and father. We call a visual representation of this a family tree. The root in a family tree is you. The rest of the tree is made up of connected nodes, namely your parents and grandparents on either side going as far back as you can imagine. Trees are a useful data structure for representing genealogy, but trees in general have other uses as well. In this tutorial you will learn how to build a basic binary search tree and you will learn to build a few of the functions used to operate upon a binary search tree.

![Family Tree](https://user-images.githubusercontent.com/60240900/161341533-2be7d064-11b9-4d1b-affc-d5236632f348.png)

### Balanced and Unbalanced Binary Trees

Trees are good at representing hierarchy. In the example above you can see genealogy hierarchy where the value determining location of your ancestor nodes is their relationship to you. However, there are different kinds of binary search trees. Hierarchy in governments is one example. If we were to model an unbalanced binary tree in the real world, we would get something akin to a dictatorship where the ruler is the root node at the top with supreme power over everything below. Everything in a dictator tree is placed on the left of the root, since everyone is less than the root ruler. However, if everything were to be placed to the right the tree would be equally unbalanced. Unbalanced binary search trees tend to be slower because their structure requires more steps to be taken in order to reach any given node. On the other hand, we have a balanced binary search tree. If modeled in the real world a balance binary search tree would look something like the current Monarchy in England. The king is at the top, but Parliament has power over the king. That would place them on the right, greater than the king. The king has servants under his command, which would place them on the left. Each servant may be in charge of other servants, and so on and so forth. Therefore it may look like the king is at the top, but in reality Parliament has the power. The pictures below may help you picture these trees.

![Unbalanced Binary Tree](https://user-images.githubusercontent.com/60240900/161355156-e5ebc711-a0eb-41ee-9c53-10bce70aac2e.png)

![Balanced Binary Search Tree](https://user-images.githubusercontent.com/60240900/161355164-447c9d1d-d746-47b7-a3ee-fa520a2d60f7.png)


### What kind of errors are common when using a tree?

TypeError

![Type Error](https://user-images.githubusercontent.com/60240900/161353035-63cbb601-189e-4e05-aaa6-07a4edff7841.png)

## Inserting

Whenever we want to insert into a Binary Search Tree we do so with [Recursion](https://www.w3schools.com/python/gloss_python_function_recursion.asp). At it's most basic level, recursion is just a function calling itself in a loop until a condition, also called the base case, is reached. There can be more than one base case. Recursion is key to understanding how to navigate a tree so take a minute to look at the link and really learn the basics of recursion. Writing down the steps down in English on a piece of paper may help you discover what is actually happening.

In a binary search tree, values are inserted depending on the answer to a question: is the data in the node we want to insert greater or lesser than the data in the node we are currently looking at? If the value of the node you want to insert is less than the current node, then look to the next node on the left. If the value of the node you want to insert is greater than the current node, then look to the next node on the right. ONLY add the node to the tree if the value of the node in that position is None. This means there is no node there already, which also means no conflict. If a node with a value already exists where you want to insert your node, then continue the search recursively by calling the insert function with the next node (right or left, depending on the data) and the node you want to insert until a None is found. In recursion we call this a smaller problem because we are still searching for the correct, empty spot to insert the node.

The following code is a Binary Search Tree which has the function to insert and traverse the binary tree. Please study and understand.

```
class BST:
    """
    Binary Search Tree (BST).  
    """

    class Node:
        """
        Each node of the BST will have data and links to the 
        left and right sub-tree. A BST will have many nodes.
        """

        def __init__(self, data):
            """ 
            Initialize the node to the data provided.  Initially
            the links are unknown so they are set to None. Each
            Node must be able to connect to other nodes.
            """
       
            self.data = data
            self.left = None
            self.right = None

    def __init__(self):
        """
        Initialize an empty BST.
        A BST must have a root.
        """
        self.root = None


    # The following two functions are BST insert functions

    def insert(self, data):
        """
        Insert 'data' into the BST.  If the BST
        is empty, then set the root equal to the new 
        node.  Otherwise, use _insert to recursively
        find the location to insert.
        """
        if self.root is None:
            self.root = BST.Node(data)
        else:
            self._insert(data, self.root)  # Start at the root

    def _insert(self, data, node):
        """
        This function will look for a place to insert a node
        with 'data' inside of it.  The current sub-tree is
        represented by 'node'.  This function is intended to be
        called the first time by the insert function.
        """
        if data < node.data:
            # The data belongs on the left side.
            if node.left is None:
                # We found an empty spot
                node.left = BST.Node(data)
            else:
                # Need to keep looking.  Call _insert
                # recursively on the left sub-tree.
                self._insert(data, node.left)
        elif data > node.data:
            # The data belongs on the right side.
            if node.right is None:
                # We found an empty spot
                node.right = BST.Node(data)
            else:
                # Need to keep looking.  Call _insert
                # recursively on the right sub-tree.
                self._insert(data, node.right)
        

    # The following two functions are required to traverse a BST.
    def __iter__(self):
        """
        Perform a forward traversal (in order traversal) starting from 
	    the root of the BST.  This is called a generator function.
        This function is called when a loop	is performed:

        for value in my_bst:
            print(value)

        """
        yield from self._traverse_forward(self.root)  # Start at the root
        
    def _traverse_forward(self, node):
        """
        Does a forward traversal (in-order traversal) through the 
        BST.  If the node that we are given (which is the current
        sub-tree) exists, then we will keep traversing on the left
        side (thus getting the smaller numbers first), then we will 
        provide the data in the current node, and finally we will 
        traverse on the right side (thus getting the larger numbers last).

        The use of the 'yield' will allow this function to support loops
        like:

        for value in my_bst:
            print(value)

        The keyword 'yield' will return the value for the 'for' loop to
	    use.  When the 'for' loop wants to get the next value, the code in
	    this function will start back up where the last 'yield' returned a 
	    value.  The keyword 'yield from' is used when our generator function
        needs to call another function for which a `yield` will be called.  
        In other words, the `yield` is delegated by the generator function
        to another function.

        This function is intended to be called the first time by 
        the __iter__ function.
        """
        if node is not None:
            yield from self._traverse_forward(node.left)
            yield node.data
            yield from self._traverse_forward(node.right)

# Sample Test Cases (may not be comprehensive) 
tree = BST()
tree.insert(23)
tree.insert(54)
tree.insert(9)
# After implementing 'no duplicates' rule,
# this next insert will have no effect on the tree.
tree.insert(1)  
tree.insert(4)
tree.insert(100)
tree.insert(17)
tree.insert(61)
for x in tree:
    print(x)  # 1, 4, 8, 17, 23, 54, 61, 100
```

## Searching


## Removing

## Example

```
class BST:
    """
    Implement the Binary Search Tree (BST) data structure.  The Node 
    class below is an inner class.  An inner class means that its real 
    name is related to the outer class.  To create a Node object, we will 
    need to specify BST.Node
    """

    class Node:
        """
        Each node of the BST will have data and links to the 
        left and right sub-tree. 
        """

        def __init__(self, data):
            """ 
            Initialize the node to the data provided.  Initially
            the links are unknown so they are set to None.
            """
       
            self.data = data
            self.left = None
            self.right = None

    def __init__(self):
        """
        Initialize an empty BST.
        """
        self.root = None
```

## 


## Problem

## Helpful Python Module

The first link is to a Python binarytree library from the Python Package Index. It allows you to declare a tree object and perform some operations to navigate, display, and interact with the tree. This is optional learning and may or may not help you with the problem above.

(PyPi binarytree)[https://pypi.org/project/binarytree/]

## References
