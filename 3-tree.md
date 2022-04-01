# Tree

[Welcome Page](https://github.com/Morthais/data_structure_final/blob/main/0-welcome.md)

TODO: Talk about recursion in this module.

## Introduction

Imagine your biological family history. If you are like most people then you have one mother and one father. Following this pattern, each pf your parents also has a mother and a father (you call these your grandparents). Yet further, even back to the beginning of time, every person has one biological mother and father. We call a visual representation of this a family tree. The root in a family tree is you. The rest of the tree is made up of connected nodes, namely your parents and grandparents on either side going as far back as you can imagine. Trees are a useful data structure for representing genealogy, but they have other uses as well. In this tutorial you will learn how to build a basic binary search tree and a few of the functions used to operate upon a binary search tree.

![Family Tree](https://user-images.githubusercontent.com/60240900/161341533-2be7d064-11b9-4d1b-affc-d5236632f348.png)

## Inserting

Whenever we want to insert into a Binary Searh Tree we do so with [Recursion](https://www.w3schools.com/python/gloss_python_function_recursion.asp). At it's most basic level, recursion is just a function calling itself in a loop until a condition, also called the base case, is reached. There can be more than one base case, as there are when inserting into a binary serach tree. Recursion is really key to understanding how to navigate this data structure so take a minute to look at the link and really learn the basics of recursion. Writing down the steps down in English on a piece of paper may help you discover what is actually happening.

In a binary search tree, values are inserted depending on the answer to a question: is the data in the node we want to insert greater or lesser than the data in the node we are currently looking at? If the value of the node you want to insert is less than the current node, then look to the next node on the left. If the value of the node you want to insert is greater than the current node, then look to the next node on the right. ONLY add the node to the tree if the value of the node in that position is None. This means there is no node there already, which also means no conflict. If a node with a value already exists where you want to insert your node, then continue the search recursively by calling the insert function with the next node and the one you want to insert until an empty place in the tree is found. In recursion we call this a smaller problem because we are still searching for the correct, empty spot to insert the node.

## Removing

## Traversing

## Example


## Problem

## Helpful Python Module

The first link is to a Python binarytree library from the Python Package Index. It allows you to declare a tree object and perform some operations to navigate, display, and interact with the tree. This is optional learning and may or may not help you with the problem above.

(PyPi binarytree)[https://pypi.org/project/binarytree/]

## References
