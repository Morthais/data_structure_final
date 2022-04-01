# Set

[Welcome Page](https://github.com/Morthais/data_structure_final/blob/main/0-welcome.md)

## Introduction

### What is a Set?

Imagine you have a bag. Your bag has one special rule which you must always remember and never forget: if you add an item to your bag you may not add a duplicate item to the same bag. In other words, you may only have one kind of every item placed into that bag. One laptop, one lunchbox, one charger, one water bottle. This is basically the idea of a set. Imagine you have an empty set. Your set does not allow duplicate items to exist within it. You may only have one string with the name "Jacob", not two. You may only have one integer 23, not two. Besides this rule of "no duplicates exist in a set," you will find they are similar to Python lists, stacks, and queues with another big difference: a set is unordered, unchangeable, and unindexed. You cannot access the items by index in the same way you would a list because sets do not have indexes nor does order matter. This structure comes with a few benefits as you will soon learn.

The set has several simple operations in Python which we will discuss later, but for now we will introduce the simplest ones. When you add an item to a set we call it an "add" operation. When you remove an item from a set we call it a "remove" operation. You can check if items are in a set, just as you would if you looked into the bag, and you can check the size of a set simple by checking the length of the set.

![Set_Bag](https://user-images.githubusercontent.com/60240900/161175019-66556e73-f82d-477e-be64-d0e4b17f89a5.png)

### What is the purpose of a Set?

Every data structure is a tool that is better at solving some problems than others. A basic set is used to test for membership and eliminate duplicate entries. They come into play when sorting through large amounts of data through an API or when interacting with a database. Sets support mathematical operations like union, intersection, and several other useful operations which allow us compare different data sets to find patterns and learn new information about a set of data. Their performance is also incredible with most operations performing in constant time, or O(1), which is the fastest it can get.

### What kind of errors are common when using a Set?

Runtime Error

![Runtime Error](https://user-images.githubusercontent.com/60240900/161179679-ccb25ca1-af8a-4436-9315-c99f98c32465.png)

Key Error

![Key Error](https://user-images.githubusercontent.com/60240900/161179909-0f299ceb-f762-43cf-a29d-1bf41c3882e5.png)


## Set Functions in Python

When considering a data structure it is important to know the performance of that data structure. As you learn the functions used by sets, consider how efficient the set operation is by finding it's Big O Notation. Basically, the Big O Notation of an operation is a measure of how fast it is. Here is a relatively new [article](https://medium.com/fintechexplained/time-complexities-of-python-data-structures-ddb7503790ef) on Big O Notation. I recommend reading at least half of the article to get a better handle on Big O Notation. It will become increasingly important going forward to know the performance of data structures.

|Function|Python Code|Description|Performance|
|---|---|---|---|
|add()|set.add()|Adds an item to the set.|O(1), Constant Time performance to add to a set.|
|remove()|set.remove(item)|Removes an item from the set.|O(1), Constant Time performance to remove from a set.|
|value_exists()|item in set:|Returns True or False depending on whether the item is in the set.|O(1), Constant Time performance to find item in a set.|
|check_size()|len(set)|Returns the number of items in the set as an integer.|O(1), Constant Time performance to find length of a set.|
|union()|set_1.union(set_2)|Creates a new set with elements from both set_1 and set_2.|O(n), Linear Time performance to unite two sets.|
|intersection()|set_1.intersection(set_2)|Creates a new set with elements common to both set_1 and set_2.|O(n), Linear Time performance to find intersection between two sets.|

## Example 1

How would a set be implemented in Python? Remember, a set on the most basic level just a list that doesn't allow duplicates. Copy the example below into your code editor and run it to better understand how sets work.

```

```

## Problem

Throughout your career you will be required to explain what your code does and why it does what it does. In order to be prepared for such times it will become increasingly important to learn what is going on "behind-the-scenes" with the functions you learn. Not only will this type of practice protect you from deep embarassment... you will become a better programmer for it.

Now it's your turn! Implement the intersection() and union() functions without using the built-in Python methods.

HINT: You have already learned everything you need to do this... if you need further help, reread the sections above or use Google.

```
def intersection(set1, set2):
    """
    Perform an intersection between 2 sets.  An intersection will contain
    the items in common between both sets.  Do not use the set 
    operators (+, -, *, &, |) and functions (intersection, union) 
    that are built-in to Python.
    """
    # TODO: add any code necessary here
    pass

def union(set1, set2):
    """
    Perform a union between 2 sets.  A union will contain all the items
    from both sets.   Do not use the set operators (+, -, *, &, |)
    and functions (intersection, union) that are built-in to Python.
    """
    # TODO: add any code necessary here
    pass

# DO NOT CHANGE
bag_1 = {"Shoes", "Laptop", "Book", 23, 7, 156, True}
bag_2 = {"Medicine", "Laptop", "Shoes", "Lunch", 23, 51, 48, False, True}
print(intersection(s1,s2))  # Should show {4, 5}
print(union(s1,s2)) # Should show {1, 2, 3, 4, 5, 6, 7, 8}

# DO NOT CHANGE
bag_1 = {"Shoes", "Laptop", "Book", 23, 7, 156, True}
bag_2 = {"Medicine", "Pen", "Paper", "Lunch", 8, 51, 48, False}
print(intersection(s1,s2))  # Should show an empty set
print(union(s1,s2)) # Should show {1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
```

## Helpful Python Module

Sets are a data structure which is built-in to core Python. Here is a link to the documentation of built-in operations which may help you solve the problem.

[Python Set Documentation](https://docs.python.org/2/library/sets.html)

## References
