# Purchase Network

```sh
rm -rf output intermediate_output 
mvn package
hadoop jar target/cs499-1.0-SNAPSHOT.jar PurchaseNetwork input output
```

## Description

3.2 [60 pts] Map-Reduce Task 2: 

BeaverMart a big supermarket chain wants to find out what
items in its stores are bought together so it can optimize the store layouts. It has records of customer purchases tracked 
using store reward cards. Each record is a tuple of items that are bought in a single transaction (e.g., {item1, item2, item3, …}). 
Write a Map-Reduce program to compute how many times a pair of items are bought together.

Input File: Will be a .txt file containing records, one per line.  The length of the file need not be fixed. 
Example: 
```
Whitey Toothpaste, Best Bread, Fluffy Pizza, BeavMoo Milk
Apples, BeavMoo Milk, Bananas, Best Bread
```

Output File: Pairs of items along with the number of times they have been purchased together
Example:
```
(Whitey Toothpaste, Best Bread) 1
(Whitey Toothpaste, Fluffy Pizza) 1
(Whitey Toothpaste, BeavMoo Milk) 1
(Whitey Toothpaste, Apples) 0
(Whitey Toothpaste, Bananas) 0
(Best Bread, Fluffy Pizza) 1
(Best Bread, BeavMoo Milk) 2
(Best Bread, Apples) 1
(Best Bread, Bananas) 1
(Fluffy Pizza, BeavMoo Milk) 1
(Fluffy Pizza, Apples) 0
(Fluffy Pizza, Bananas) 0
(BeavMoo Milk, Apples) 1
(BeavMoo Milk, Bananas) 1
(Apples, Bananas) 1
Total Pairs: 15
```

Grading: 
- Program compiles and runs without failure: 10 points
- Passes two test cases: 20 points each
- Design (how fast and scalable is your design): 10 points
