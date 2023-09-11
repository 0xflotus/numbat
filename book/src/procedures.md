# Printing, testing, debugging

## Printing

Numbat has a builtin `print` procedure that can be used to print the value of an expression:

```nbt
print(2 km/h)
print(3 ft < 1 m)
```

## Testing

The `assert_eq` procedure can be used to test for (approximate) equality of two quantities.
This is often useful to make sure that (intermediate) results in longer calculations have
a certain value, e.g. when restructuring the code. The general syntax is

```nbt
assert_eq(q1, q2)
assert_eq(q1, q2, ε)
```

where the first version tests for exact equality while the second version tests for approximate
equality \\( |q_1-q_2| < \epsilon \\) with a specified accuracy of \\( \epsilon \\). For example:

```nbt
assert_eq(2 + 3, 5)
assert_eq(1 ft × 77 in², 4 gal)

assert_eq(alpha, 1 / 137, 1e-4)
assert_eq(3.3 ft, 1 m, 1 cm)
``` 

A runtime error is thrown if an assertion fails. Otherwise, nothing happens.

## Debugging

You can use the builtin `type` procedure to see the type (or physical dimension) of a quantity:

```nbt
>>> type(g0)

  Length / Time²

>>> type(2 < 3)

  bool
```
