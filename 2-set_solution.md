```
def intersection(set1, set2):
    """
    Perform an intersection between 2 sets.  An intersection will contain
    the items in common between both sets.  Do not use the set 
    operators (+, -, *, &, |) and functions (intersection, union) 
    that are built-in to Python.
    """
    new_set = set()
    for item in set1:
        if item in set2:
            new_set.add(item)
    
    return new_set

def union(set1, set2):
    """
    Perform a union between 2 sets.  A union will contain all the items
    from both sets.   Do not use the set operators (+, -, *, &, |)
    and functions (intersection, union) that are built-in to Python.
    """
    new_set = set1
    for item in set2:
        new_set.add(item)

    return new_set

bag_1 = {"Shoes", "Laptop", "Book", 23, 7, 156, True}
bag_2 = {"Medicine", "Laptop", "Shoes", "Lunch", 23, 51, 48, False, True}
print(intersection(bag_1,bag_2))  # Should show {'Laptop', True, 23, 'Shoes'}
print(union(bag_1,bag_2)) # Should show {False, True, 7, 'Shoes', 'Lunch', 48, 51, 'Medicine', 23, 'Laptop', 'Book', 156}

bag_1 = {"Shoes", "Laptop", "Book", 23, 7, 156, True}
bag_2 = {"Medicine", "Pen", "Paper", "Lunch", 8, 51, 48, False}
print(intersection(bag_1,bag_2))  # Should show an empty set
print(union(bag_1,bag_2)) # Should show {False, True, 7, 8, 'Shoes', 'Pen', 'Lunch', 48, 51, 'Medicine', 23, 'Laptop', 'Paper', 'Book', 156}
```
