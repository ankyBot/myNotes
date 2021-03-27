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



##  Optimization with Caching

```js
// Task 1: Write a function, times10, that takes an argument, n, and multiples n times 10
// a simple multiplication fn
const times10 = (n) => {
  let myVal = 0;
  for(let i = 1; i <= n; i++) {
    myVal += 10;
  }
  return myVal;
};

console.log('~~~~~~~~~~~~~~TASK 1~~~~~~~~~~~~~~');
console.log('times10 returns:', times10(9));

// Task 2: Use an object to cache the results of your times10 function. 
// protip 1: Create a function that checks if the value for n has been calculated before.
// protip 2: If the value for n has not been calculated, calculate and then save the result in the cache object.

const cache = {};

const memoTimes10 = (n) => {
  if(n in cache) {
    return cache[n];
  } else {
    let myVal = times10(n);
    cache[n] = myVal;
    return myVal;
  }
}

console.log('~~~~~~~~~~~~~~TASK 2~~~~~~~~~~~~~~');
console.log('Task 2 calculated value:', memoTimes10(9));	// calculated
console.log('Task 2 cached value:', memoTimes10(9));	// cached








//👇👇👇👇👇👇[ My Other methode, maybe😅 ]👇👇👇👇👇👇👇


// Task 1: Write a function, times10, that takes an argument, n, and multiples n times 10
// a simple multiplication fn
/*
const times10 = (n) => {
  let myVal = 0;
  for(let i = 1; i <= n; i++) {
    myVal += 10;
  }
  return myVal;
};

console.log('~~~~~~~~~~~~~~TASK 1~~~~~~~~~~~~~~');
console.log('times10 returns:', times10(9));
*/

// Task 2: Use an object to cache the results of your times10 function. 
// protip 1: Create a function that checks if the value for n has been calculated before.
// protip 2: If the value for n has not been calculated, calculate and then save the result in the cache object.

/*
const cache = {};

const memoTimes10 = (n) => {
  if(!cache[n]) {
    let myVal = 0;
    for(let i = 1; i <= n; i++) {
      myVal += 10;
    }
    cache[n] = myVal;
    return myVal;
  } else {
    return cache[n];
  }
}
*/

//console.log('~~~~~~~~~~~~~~TASK 2~~~~~~~~~~~~~~');
//console.log('Task 2 calculated value:', memoTimes10(9));	// calculated
//console.log('Task 2 cached value:', memoTimes10(9));	// cached



```

