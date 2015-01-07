# Chapter 4. Error Handling
- Most programs need a kind of a disaster plan to handle unexpected input.

## Types of Problems
- Most problems that a program can encounter can be divided into two categories:
    - Programmer Mistakes
    - Run-time problems

## Returning a Special Value
- When a function encounters a problem that it cannot solve itself, one possible reaction is to return a value that it could not normally return.
- Usually the value of `undefined` is returned in these situations.
- This does not work whem a funciton is expected to return every possible kind of value, like listing the contents of an array.
- Also this kind of checking can lead to a lot of clutter in the code.

## Exceptions
- When a function cannot return normally, we want it to stop running and jump immediately back to a place that knows how to handle the problem.
- This process is called _exception handling_.
- It is possible for code to raise (or throw) an exception, which is a value.
- Raising an exception is similair to a `return` statement - but it does not jump out of the current function but also out of its callers, all the way to the top-level call that started the current execution.
- This is called _unwinding the stack_.
- It is possible to set obstacles for exceptions along the stack - these `catch` the exceptions and can do something with it.
- After this the program continues running at the point where the exception was caught.
- THe big advantage of exceptions -- error handling code is necessary only at the point where the error occurs and at the point where it is handled. The functions in between can forget all about it.

```javascript
function lastElement(array){
    if(array.length > 0)
        return array[array.length - 1];
    else
        throw "Cannot take the last element of an empty array.";
}

function lastElementPlusTen(array){
    return lastElement(array) + 10;
}

try {
    print(lastElementPlusTen([]));
}
catch(error) {
    print("Something went wrong: ", error);
}
```
- The keyword `throw` is used to raise an exception.
- The keyword `try` sets up an obstacle for exceptions.
- When the code in the block after it raises an exception, the catch block will be executed.
- The variable named in the parentheses after the cord catch will hold the excpetion value when the block executes.
- The `try` statements can be followed by a `finally` keyword, which will run the code regardless of what is happening.
- The `finally` keyword usually will clean up the code if something went wrong.

```javascript
var currentThing = null;
function processThing(thing){
    var prevThing = thing;
    currentThing = thing;
    try {
        // do complticated processing    
    }
    finally {
        currentThing = prevThing;
    }
}
```

## Error Objects
- There is a special type of object that is raised for problems.
- These error objects always haave a message property containing a description of the problem.

```javascript
try {
    print(Sasquatch);
}
catch(error) {
    print("Caught: " + error.message);
}
```

- Custom objects can be raised using the `new` keyword and the `Error` constructor, to give a message as argument.

```javascript
throw new Error("Custom Error message was thrown!");
```

## Unhandled Exceptions
- When an exception makes it all the way to the bottom of the stack without being caught -- it gets handled by the environment.
- The result would be different depending on the JavaScript environment -- in the browser it would be displayed in the console.
- For programmer mistakes or problems that the program cannot hangle - letting the error go thorough is ok.
- An ungandled exception is a reasonable way to signal a broken program.

## Selective Catching
- When explicitly handling an exception using `catch`, care must be taken to not catch too much.

```javascript
var invalidInputError = new Error("Invalid numeric input");

function inputNumber(){
    var input = Number(prompt("Give me a number", ""));
    if(isNaN(input))
        throw InvalidInputError;
    return input;
}

for(;;){
    try{
        alert(inputNumber() + 5);
        break;
    }
    
    catch(e){
        if(e != invalidInputError)
            throw e;
        alert("You did not input a number. Try again.");
    }
}
```