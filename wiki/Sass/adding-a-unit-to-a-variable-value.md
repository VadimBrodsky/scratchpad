---
tags: #sass
---

# Adding a Unit to a Variable Value

```sass
// A variable with no unit
$variable-with-no-unit: 0;

// Add the unit to the variable, can be used with px, em or %
$variable-with-unit-added: ($variable-with-no-unit * 1%);
```