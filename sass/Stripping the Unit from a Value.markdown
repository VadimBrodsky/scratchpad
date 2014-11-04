# Stripping the Unit from a Value

```sass
// A variable with a unit
$variable-with-unit: 0%;
// Strip the unit from the variable
$variable-without-unit: ($variable-with-unit * 1 + 0);
```
