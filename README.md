# JS Fundamentals Checkpoint 9 Drills

Objective: By the end of this checkpoint, students can implement asynchronous code.
Explain the problems that callbacks solve:
asynchronous code
iterations that repeat logic
when we want to return multiple values instead of just one return statement (async)
Examples of pre-built functions that accept callbacks. Refactor them to show we're passing the functions, not the return values. For example, array methods.
Introduce methods like setTimeout and setInterval to demonstrate clocks and simple animations.
Examples of writing custom functions that accept callbacks as parameters and then call the callbacks.
Call out that functions are "first class" so can be passed around like variables.
Assignment: Drills that expand on the set from checkpoint 7 (answering questions about data)
As well as setTimeout / setImmediate / maybe `new Date()`
Higher order functions

## 1

**Learning:**

**Question:** Consider the code below. What would be printed in the console when this code executes?

```
function one() {
  console.log('one');
}

function two(callback) {
  console.log('two');
  callback();
}

function three() {
  console.log('three');
  two(one);
}

three();
```

## 2

**Learning:**

**Question:** 
 - Write a function named `process` that accepts three parameters.
   - The first parameter named `fn` is an arbitrary function
   - The second parameter named a is a numeric value
   - The third parameter named b is a numeric value
 - `process` should call the function `fn` passing the arguments `a` and `b`
 - After `fn` is done executing `process` should return the value returned by `fn`.
 - Create 2 more functions `add` and `subtract`
   - `add` accepts two parameters `a` and `b` and returns `a + b`
   - `subtract` accepts two parameters `a` and `b`and returns `a - b`
 - Use the `process` function to call `add` with 6 and 4
 - Use the `process` function to call `subtract` with 6 and 4


## ? (Rethink or remove this one)
**Learning:**

**Question:** The function below accepts three callback functions named `start`, `tick` and `done`. It invokes `start` once, then invokes `tick` ten times with a half second delay between invocations passing a countdown parameter each time. That is, the first time it calls `tick` it passes 10, then 9 and so on down to 1. After `tick` is called 10 times, the `done` function is called once.

Write three functions, the first prints 'Starting countdown', the second accepts a single numeric value and prints the value and the third prints 'BOOM!'. Call the `countdown` function passing your three functions as callbacks. If it works correctly you should see the countdown occur in the console.

```
function countdown(start, tick, done) {
  start();
  (function loop(i) {
    setTimeout(function() {
      tick(i--);
      if(i > 0){
        loop(i);
      } else {
        done();
      }
    }, 500);
  })(10);
}
```

Write three different functions. The first prints 'Download starting', the second accepts a numeric value as described above and prints '100% left', '90% left' and so on. The last one prints 'Download conplete'. Invoke the `countdown` function again with the three new functions.
