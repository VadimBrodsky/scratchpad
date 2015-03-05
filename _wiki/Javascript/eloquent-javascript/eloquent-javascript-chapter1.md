# Chapter 1. Basic JavaScript: Values, Variables, and Control Flow

## Basic Value Types in JavaScript
- Numbers
- Strings
- Booleans - `true` or `false` (`0`, `NaN`, `""` all count as `false`)
- Objects
- Functions
- Undefined (null == undefined)

## Variables
- Variables are created by invoking their name, but this is a bad practice.
- The keyword `var` is used to create new variables explicitly.
- Variable names cannot include spaces, cannot start with a digit.
- Can use `$` and `_` in variable names.

## Keywords and Reseved Words
```javascript
abstract boolean break byte case catch char class const continue debugger default delete do double else enum export extends false final finally float for function goto if impements import in instanceof int interface long native new null package private protected public return short static super switch synchronized this throw throws transient true try typeof var void volatile while with
```

## Operators - Binary and Unary
- plus `+` (can be used on strings to concatinate)
- minus `-`
- multiply `*`
- division `/`
- modulo `%`
- type of `typeof`

All arithmetic operations on the value `NaN` result in `NaN`

## Special String Characters
- Use the backslash `\` to add a special meaning to a string.
- New line `\n`
- Tab `\t\`
- Quote `\'`

```javascript
"A newline character is written like \"\\n\"."
```

## Boolean Operators
- less `<`
- greater `>`
- less than or equal to `<=`
- greater than or equal to `>=`
- equal to `==`
- not equal to `!==`
- Logical and `&&`  // can be used on non boolean values
- Logical or `||`   // can be used on non boolean values
- Logical not `!`
- Precisely equal `===`
- Not precisely equal `!==`

```javascript
var input= prompt("What is your name?", "Kilgore Trout");
console.log("Hello " + (input || 'dear'));
```

## Expressions and Statements
- An expression can be content to just produce a value, but a statement amounts to something only if it somehow changes the world.
- The changes are called - side effects
- Every statement needs to terminated by a semicolon `;`
- A lone semicolon can be used to produce an empty statement.

## The Environment
- The collection of variables and their values that exist at a given time.
- It always contains a number of standard variables.
- When a browser loads a page it creates a new environment and attaches the standard variables to it.
- The variables only survive on that page, until the browser goes to a new page.
- It is possible to modify the environment with new values, this can damage functionality.

## Conditionals
- Use to create seperate parallel paths in execution.

```javascript
if(true == false) {
    ...
} else if {
    ...
} else {
    ...
    };
```

```javascript
switch(value) {
    case "rock": console.log("breaks scissors");
        break;
    case "paper": console.log("covers rock");
        break;
    case "scissors": console.log("cuts paper");
        break;
    default: console.log("It's a tie");
        break;
}
```

## Loops
- Cases statements to be executed multiple times.
- To the world outide the loop, the loop counts as a single statement.
- `while` loop is the simplest loop - continues while the condition is true.
- `do` loop will execute its body at least once, only then will test the condition.
- `for` loop is a shorter and more comprehensive form of the `while` loop.
- `break` keyword is used to stop the execution of the loop ahead of time.

```JavaScript
var result = 1;
var counter = 0;
while (counter < 10 ) {
    result = result * 2;
    counter++;
}
result;
```

```javascript
do {
    var input = prompt("Who are you?");    
}
```

```javascript
for (var number = 0; number <= 12; number = number + 2) {
    ...
}
```

## Functions
- A function is a piece of program wrapped in a value.
- Can be evoked by using the function value that contains it.
- In the browser, the variable `alert` holds a function that shows a dialog box with a message.
- Values given to functions are called arguments.
- Functions can produce side effects or return values.

```javascript
alert("Good Morning!");
```