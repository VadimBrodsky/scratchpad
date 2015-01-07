# Chapter 2. Functions
- The keyword `function` is always used when creating a new function.
- When followed by a variable name, the new function will be stored under that name.
- Function definition can be anywhere in the source order, they will be looked-up when called.
- The best function are those that perform a single, simple action - they are easier to name and can be used in a wider variety of situations.
- Good principle - not to add cleverness unless you are absolutely sure you are going to need it, otherwise you'll spend more time writing complicated frameworks for every little bit of functionality instead of any actual work.
- Pure functions are generally without complex side-effects, they always produce the same result based on the same input.

```javascript
function square(x) {
    return x*x;
}
```

## Return Statement
- Some functions can create side effects, while other will create values and return them.
- The `return` keyword indicates the value that the function returns.
- The `return` keyword without a statement will cause the function to return undefined.
- The value from a function without a return statement will be undefined.

## Variable Scope
- Variables that are declared inside the function exist only in that local scope.
- Function can access global varibales.
- Functions defined inside other functions can refer to variables in both their parent and grandparent functions.
- The set of variables visible inside a function is determined by the place of that function in the program text.
- All variables that were defined "above" a function's definition are visible -- lexical scoping.
- Functions are the only things that create a new scope in JavaScript.

```javascript
function multiplyAbsolute(number, factor) {
    function multiply(number) {
        return number * factor;
    }
    if (number < 0)
        return multiply(-number);
    else
        return multiply(number);
}
```

## Anonymous Functions
- The function is called and defined in the same place.
- No name is given to the function.

```javascript
var a = null;
(a || function(){return "B";})(); // returns B
```

## Closures
- What happens to a local variables when the function call that created them is no longer on the stack?
- Upwards Funarg Problem - many programming languages forbid it.
- JavaScript makes sure that the local variable is reachable.
- Closure - a function that "closes over" some local variables.
- Allows to create function that dynamically create function values.

```javascript
function makeAdder(amount) {
    return function(number) {
        return number + amount;
    }
}
vad addTwo = makeAdder(2);
addTwo(3); // returns 5
```

## Optional Values
- JavaScript is nonstrict about the amount of arguments you can pass to a function.
- If you pass to many - the extra ones are ignored.
- If you pass to few - the missing ones get the value undefined.

```javascript
function power(base, exponent) {
    var result = 1;
    if (exponent === undefined)
        exponent = 2;
    for(var count=0; count  goal)
            return null;
        else
            return find(start+5,"(" + history + " + 5)") || find(start*3, "(" + history + " *3)");
    }
    return find(1,"1");
}

findSequence(24); // returns (((1*3)+5)*3)
```