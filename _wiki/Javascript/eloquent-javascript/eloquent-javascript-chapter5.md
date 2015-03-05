# Chapter 5. Functional Programming
- The programmer is always looking for ways to keep the complexity of his programs as low as possible.
- A way to do this is try to make code more abstract.
- If you assume a certain basic knowledge in the audience, you can talk in a language that deals with bigger concepts and express things in a much shorter and clever way.

## Higher-Order Functions
- Since "doing something" can be represented as a function and since functions are also values, we canpass our actions as a function value.
- Functions that operate on other functions are called _higher-order functions_.
- Higher-order functions can be used to generalize many algorithms that regular functions cannot easlity describe.
- Instead of a messy set of variables and loops, you can decompose algorithms into a combination of a few fundamental algorithms, which invoked by name and do not have to be typed out again and again.
- Being able to write what we want to do instead of how we do it, means we are working at a higher level of abstraction.

```javascript
function forEach(array, action){
    for(var i=0; i < array.length; i++)
        action(array[i]);
}

function sum(numbers){
    var total = 0;
    forEach(numbers, function(number){
        total += number;
    });
    return total;
}
```

## Modifying Functions
- Higher-order functions can modify the function value that is given.

```javascript
function negate(func) {
    return function(x){
        return !func(x);
    };
}
var isNotNaN = negate(isNaN);
isNotNaN(NaN);      // false
```

- The function returned by negate feeds the argument it is given to the original funciton `func` and then negates the result.
- Functions have a method called `apply`, which is used for situations in which we don&#039;t know how many agrument the parameter function has.
- It takes two arguments:
    - The first ?
    - The second - is an array containing the arguments to which a function must be applied.

```javascript
function negate(func){
    return function(){
        return !func.apply(null, arguments);
    };
}
```

## The reduce Function
- Reduce combines an array into a single value.
- By repeatedly using a function that combines an element of the array with a base value.
- In JavaScript addition is an operator and not a function, we had to put it into a funciton.
- Reduce takes the function as its first argument instead of last, is due to tradition, and it allows to use partial application.

```javascript
function reduce(combine, base, array){
    forEach(array, function(element){
       base = combine(base, element); 
    });
    return base;
}
function add(a, b){
    return a + b;
}
function sum(numbers){
    return reduce(add, 0, numbers);
}
```

A function that takes an array of numbers as its argument and returns the amount of zeroes that occur in it:

```javascript
function countZeroes(array){
    function counter(total, element){
        return total + (element === 0 ? 1 : 0);
    }
    return reduce(counter, 0, array);
}
```

## Mapping Arrays
- It goes over an array, applying a function to every element.
- It builds a new array based on the results of the function and the values.

```javascript
function map(func, array) {
    forEach(array, function(element) {
        result.push(func(element));
    });
    return result;
}

map(Math.round,  [0.01, 2, 9.89, Math.PI]);     // [0,2,10,3]
```