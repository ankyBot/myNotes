# [A Practical Guide to Algorithms with JavaScript](https://slides.com/bgando/intro-to-algorithms)



## introducing-space-time-complexity

### **Time** Complexity

How many primitive ***operations*** are executed?

### **Space** Complexity

How much ***memory*** is used?



## Complexity in general

| Big-O, name       | # of Operations | Algorithm                        |
| ----------------- | --------------- | -------------------------------- |
| O(n^2), quadratic | n^2             | compare all numbers              |
| O(n), linear      | 2n              | Find min and max numbers         |
| O(1), constant    | 2               | Sorted list, find first and last |



##  Complexity of Common Operations

| Complexity | Operation                                      |
| ---------- | ---------------------------------------------- |
| O(1)       | Running a statement                            |
| O(1)       | Value look-up on an array, object, variable    |
| O(logn)    | Loop that cuts problem in half every iteration |
| O(n)       | Looping through the values of an array         |
| O(n^2)     | Double nested loops                            |
| O(n^3)     | Triple nested loops                            |