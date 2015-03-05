---
tags: #php #basics @getting-good-php
---

# Control Structures

## If and Else

```php
if ($argument == true) {
    echo "This executes";
} else if ($argument == false) {    // elseif as one word also works
    echo "This execures";
} else {
    echo "$argument was null";
}
```

Alternative syntax: can use `endif`, `endfor`, `endforeach` and `endswitch` to replace curly braces.

```php
if ($argument == true):
    echo "This executes";
elseif ($argument == false):
    echo "This executes";
else:
    echo "There was a null";
endif;
```

## For and Foreach

```php
$starks = array("Jon", "Rob", "Brandon", "Riccon");
echo "<ul>";
for($i=0, $length = count($starks); $i < $length; $i++) {
    echo "<li> $starks[$i] </li>"
}
echo "</ul>"
```

```php
$stark = array("name" => "John Snow", "father" => "Eddard Stark","mother" => "Unknown");
echo "<ul>"
foreach($stark as $value) {
    echo "<li> $value </li>";
}
echo "</ul>";

foreach($stark as $key => $value) {
    echo "<li> His $key is $value. </li>";
}
```


## Return

Whatever value is passed to the `return` statement is the value that will be returned to the function that was called.

```php
function say_hello ($name) {
    return "Hello, $name";
}
echo say_hello("Eddard");
```

## Continue

Will skip the rest of the loop and will start the next iteration.

```php
$starks = array("Jon", "Rob", "Brandon", "Riccon");
foreach($starks as $stark) {
    if($stark === "John") {
        continue;
    }
    echo $stark;
}
```

## Break

Acts like `continue` but ends the entire loop.

```php
$starks = array("Jon", "Rob", "Brandon", "Riccon");
foreach($starks as $stark) {
    if($stark === "John") {
        break;
    }
    echo $stark;
}
```


## Switch

```php
$house = "Stark";
switch ($house) {   // The switch evaluation is equal to ==
    case "Stark":
        echo "Winter Is Coming";
        break;
    case "Lannister":
        echo "Hear Me Roar!";
        break;
    case "Targaryen":
        echo "Fire And Blood";
        break;
    default:
        echo "A Lannister always pays his debts";
}
```