# Chapter 3. Data Structures: Objects and Arrays

## Properties
- Some JavaScript values have other values associated with them.
- These associations are called _properties_.
- Every string has a property `length` - refers to the integer amount of characters in that string.
- Porerties can be accessed either with brackets or dot notation.
- The dot notation is a shorthand, it only works when the name of the propery is a valid variable name.
- The bracket notation can be any expression, it is converted to a string to determine the property name, variables can be property names.
- Trying to read properties from `null` or `undefined` will cause an error.

```javascript
vat text="pueple haze";
text["length"];     // retruns 11
text.length;        // returns 11
```

## Object Values
- In most value types - the properties are fixed.
- In objects - the properties can be freely added, removed, and changed.
- The main role of objects is to be a collection of properties.
- Each object propery is labeled by name, they can be any strings.
- Trying to read nonexistent property gives the value `undefined`.

The keyword `delete` is used to cut off properties.
```javascript
var cat = {color: "gray", name: "Spot", size: 46};

cat.size = 47;
cat.size;       // returns 47

delete cat.size;
cat.size;       // returns undefined
```

If a property that does not yet exist is se with the `=` operator, it is added to the object.
```javascript
var empty = {};
empty.notReally = 1000;
empty;      // returns {notReally: 1000}
```

The operator `in` can be used to test whether an object has a certain property, it produces a boolean.
```javascript
var chineseBox = {};
chineseBox.content = chineseBox;
"content" in chineseBox;            // returns true
"content" in chineseBox.content;     // returns true
```

## Objects as Sets
- A set is a collection of values in which no value occurs more than once.
- To add a name to the set, we set the property in the object to some value.
- Removing a name from the set is done by deleting the property.
- The `in` operator can be used to determine whether a certain name is part of the set.

## Mutability
- Object values can change, the content of a value can be modified, by changing properties.
- With objects, there is a difference between having two references to the smae object and having two different objects that contain the same proeprties.
- JavaScript's `==` opertor, when comparing objects, will return true only if both values given to it are the precise same value.
- Comparing different objects with identical contents will give false.

```javascript
var object1 = {value: 10};
var object2 = object1;
var object3 = {value: 10};

object1 == object2;     // true
object1 == object3;     // false

object1.value = 15;
object2.value;          // 15
object3.value;          // 10
```

## Arrays: Objects as Collections
- New arrays can be created using brackes `var array = [];`.
- The `length` property tells us how many values the array holds.

```javascript
for(var current=0; current < mailArchive.length; current++)
    print("Processing email #", current, ": ", mailArchive[current]);
```

## Methods
- Strings and array object contian a number of properties that refer to function values.
- Properties that contain fucntions are called _methods_.
- Some useful string and array methods:
    - `string.toUpperCase`
    - `array.push("add one at the end")`
    - `array.join(" ")`
    - `array.pop()`

## The Arguments Object
- Every function adds an arguments variable to its environment when the funciton is called.
- This variable refers to an object that resembles an array.
- It has a property 0 for the first argument, 1 for the second etc.
- It also has a `length` property.
- Some function can take any number of arguments, like `print` does - they typically look over the values in the arguments.
- Other functions can take optional values - when not given by the caller get some sensible default values.

```javascript
function add(number, howmuch) {
    if(arguments.length < 2)
        howmuch = 1;
    return number + howmuch;
}
```

## The Date Object
- A JavaScript object to store date information.
- A date is represented by the amount of milliseconds it is away from January 1, 1970.
- A function `new` is used to build up the object, this funciton is a _constructor_.
- The order of arguments is year, month, day, hour, minute, second, milliseconds. 
- The last four arguments are optional, they default to `0` if not defined.
- Month numbers go from `0` to `11`, while day numbers start from `1`.
- Date objects can be inspected with a number of `get` methods.
- All, except for `getDay` also have a `set` variant, that can be used to change the value in the date object.

```javascript
new Date(1987, 0, 12, 20, 30);
var today = new Date();
print("Year: " , today.getFullYear(), ", month: " , today.getMonth() , ", day: " , today.getDate());
print("Hour: " , today.getHours() , ", minutes: " , today.getMinutes() , ", seconds: " , today.getSeconds());
print("Day of the week: " , today.getDay());
```

- The method `getTime()` will get the amount of time that passed from January 1, 1970 in milliseconds.
- Comparing dates with ``,`=` does exactly what is expected.
- Testing whether two dates are equal

```javascript
var wende1 = new Date(1989, 10, 9);
var wende2 = new Date(1980, 10, 9);
wende1.getTime() == wende2.getTime();   // true
```

- The date object also contains information about a time zone.
- The `getTimezoneOffset` function of a Date can be used to find out how many minutes it differs from GMT.

```javascript
new Date().getTimezoneOffset();     // 300 for Toronto
```

## The Math Object
- Objects sometimes play a role of holding a number of related values.
- The `Math` object houses many mathenmatical methods and constants.

```javascript
Math.cos; Math.sin; Math.tan; Math.acos; Math.asin; Math.atan;
Math.PI; Math.E;
Math.pow; Math.sqrt;
Math.max; Math.min; Math.round; Math.floor; Math.ceil;
```

## Enumerable Properties
- Some properties of objects are hidden from `in loops` -- these are _not enumerable_.
- The reason behind this, is to hide these proiperties when looking for relevant information that is stored in the object.
- All properties your programs add to objects are visible.
- There is no way to make them hidden.