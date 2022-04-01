# Tree

[Welcome Page](https://github.com/Morthais/data_structure_final/blob/main/0-welcome.md)

TODO: Talk about recursion in this module.

## Introduction

Imagine your biological family history. If you are like most people then you have one mother and one father. Following this pattern, each pf your parents also has a mother and a father (you call these your grandparents). Yet further, even back to the beginning of time, every person has one biological mother and father. We call a visual representation of this a family tree. The root in a family tree is you. The rest of the tree is made up of connected nodes, namely your parents and grandparents on either side going as far back as you can imagine. Trees are a useful data structure for representing genealogy, but they have other uses as well. In this tutorial you will learn how to build a basic binary search tree and a few of the functions used to operate upon a binary search tree.

![Family Tree](https://user-images.githubusercontent.com/60240900/161341533-2be7d064-11b9-4d1b-affc-d5236632f348.png)

## Inserting

Whenever we want to insert into a Binary Search Tree we do so with [Recursion](https://www.w3schools.com/python/gloss_python_function_recursion.asp). At it's most basic level, recursion is just a function calling itself in a loop until a condition, also called the base case, is reached. There can be more than one base case, as there are when inserting into a binary serach tree. Recursion is really key to understanding how to navigate this data structure so take a minute to look at the link and really learn the basics of recursion. Writing down the steps down in English on a piece of paper may help you discover what is actually happening.

In a binary search tree, values are inserted depending on the answer to a question: is the data in the node we want to insert greater or lesser than the data in the node we are currently looking at? If the value of the node you want to insert is less than the current node, then look to the next node on the left. If the value of the node you want to insert is greater than the current node, then look to the next node on the right. ONLY add the node to the tree if the value of the node in that position is None. This means there is no node there already, which also means no conflict. If a node with a value already exists where you want to insert your node, then continue the search recursively by calling the insert function with the next node and the one you want to insert until an empty place in the tree is found. In recursion we call this a smaller problem because we are still searching for the correct, empty spot to insert the node.

The following code is a Binary Search Tree with an insert class. Please study and understand how to insert into a binary tree.

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
                
# Sample Test Cases (may not be comprehensive) 
print("\nTEST CASES")
tree = BST()
tree.insert(5)
tree.insert(3)
tree.insert(7)
# After implementing 'no duplicates' rule,
# this next insert will have no effect on the tree.
tree.insert(7)  
tree.insert(4)
tree.insert(10)
tree.insert(1)
tree.insert(6)
for x in tree:
    print(x)  # 1, 3, 4, 5, 6, 7, 10
        
```

## Searching



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
        
    def __contains__(self, data):
        """ 
        Checks if data is in the BST.  This function
        supports the ability to use the 'in' keyword:

        if 5 in my_bst:
            ("5 is in the bst")

        """
        return self._contains(data, self.root)  # Start at the root

    def _contains(self, data, node):
        """
        This function will search for a node that contains
        'data'.  The current sub-tree being search is 
        represented by 'node'.  This function is intended
        to be called the first time by the __contains__ function.
        """
        if node == None:    # Base Case: data does not exist in the tree
            return False
        elif node.data == data:   # Base Case: data exists in the tree
            return True

        elif data < node.data:
            # Need to keep looking.  Call _contains
            # recursively on the left sub-tree.
            return self._contains(data, node.left)  # returns whether number exists
        elif data > node.data:
            # Need to keep looking.  Call _contains
            # recursively on the right sub-tree.
            return self._contains(data, node.right) # returns whether number exists

# Sample Test Cases (may not be comprehensive) 
print("\nTEST CASES")
print(3 in tree) # True
print(2 in tree) # False
print(7 in tree) # True
print(6 in tree) # True
print(9 in tree) # False

```

## Removing

## Example


## Problem

## Helpful Python Module

The first link is to a Python binarytree library from the Python Package Index. It allows you to declare a tree object and perform some operations to navigate, display, and interact with the tree. This is optional learning and may or may not help you with the problem above.

(PyPi binarytree)[https://pypi.org/project/binarytree/]

## References
