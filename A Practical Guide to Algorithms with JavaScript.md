# [A Practical Guide to Algorithms with JavaScript](https://slides.com/bgando/intro-to-algorithms)



## **Space** and Time complexity

### **Time** Complexity

How many primitive ***operations*** are executed?

### **Space** Complexity

How much ***memory*** is used?




### Complexity in general

| Big-O, name       | # of Operations | Algorithm                        |
| ----------------- | --------------- | -------------------------------- |
| O(n^2), quadratic | n^2             | compare all numbers              |
| O(n), linear      | 2n              | Find min and max numbers         |
| O(1), constant    | 2               | Sorted list, find first and last |



###  Complexity of Common Operations

| Complexity | Operation                                      |
| ---------- | ---------------------------------------------- |
| O(1)       | Running a statement                            |
| O(1)       | Value look-up on an array, object, variable    |
| O(logn)    | Loop that cuts problem in half every iteration |
| O(n)       | Looping through the values of an array         |
| O(n^2)     | Double nested loops                            |
| O(n^3)     | Triple nested loops                            |









##  Optimization with Caching

### Unique sort

```js
//Transforming the simple sorting algorithm into a unique sort. 
// It's not returning any duplicate values in the sorted array.

//input: [1,5,2,1] => output: [1,2,5]
//input: [4,2,2,3,2,2,2] => output: [2,3,4]

const uniqSort = function(arr) {
    const breadcrumbs = {};
    let myResult = [];

    for(let i = 0; i < arr.length; i++) {

      if(!breadcrumbs[arr[i]]) {
        myResult.push(arr[i]);
        breadcrumbs[arr[i]] = true;
      }
    }
    return myResult.sort((a, b) => a - b);
};

uniqSort([4,2,2,3,2,2,2]); // => [2,3,4]
```



### Memoization

In computing, **memoization** or memoisation is an optimization technique used primarily to speed up computer programs by storing the results of expensive function calls and returning the cached result when the same inputs occur again.



### Basic Memoization Soluation

```js
// simple multiplication fn Memoization fn
// A function, times10, that takes an argument, n, and multiples n times 10

const times10 = (n) => {
  let myVal = 0;
  for(let i = 1; i <= n; i++) {
    myVal += 10;
  }
  return myVal;
};

console.log('~~~~~~~~~~~~~~TASK 1~~~~~~~~~~~~~~');
console.log('times10 returns:', times10(9));

// Here we are using an object to cache the results of our times10 function. 
 
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
```



### Memoization with closure

```js
const times10 = (n) => (n * 10);

// Cleaning up our global scope by moving our cache inside our function.

const memoizedClosureTimes10 = () => {
  let cache = {};
  return (n) => {
    if(n in cache) {
      return cache[n];
    } else {
      let result = times10(n);
      cache[n] = result;
      return result;
    }
  };
};

const memoClosureTimes10 = memoizedClosureTimes10();
console.log('~~~~~~~~~~~~~~TASK 3~~~~~~~~~~~~~~');
try {
  console.log('Task 3 calculated value:', memoClosureTimes10(9));	// calculated
  console.log('Task 3 cached value:', memoClosureTimes10(9));	// cached
} catch(e) {
  console.error('Task 3:', e);
}
```



### Generic Memoization function

```js
const times10 = (n) => (n * 10);

// Making our memo function generic and accept the times10 function as a callback rather than defining the n * 10 logic inside the if/else or pulling it in from the global scope.

const memoize = (cb) => {
  let cache = {};
  return (n) => {
    if(n in cache) {
      return cache[n];
    } else{
      let result = cb(n);
      cache[n] = result;
      return result;
    }
  };
};

// returned function from memoizedAdd
const memoizedTimes10 = memoize(times10);
console.log('~~~~~~~~~~~~~~TASK 4~~~~~~~~~~~~~~');
try {
  console.log('Task 4 calculated value:', memoizedTimes10(9));	// calculated
  console.log('Task 4 cached value:', memoizedTimes10(9));	// cached
} catch(e) {
  console.error('Task 4:', e)
}
```



