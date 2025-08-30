# Conditions and loops

To successfully master the material in the next lesson, it is necessary to know
the basic facts about working with conditions and loops.

## Conditions

In most modern programming languages, conditional statements are used to make
decisions and control the flow of a program. The most common constructs are:

* if
* if-else
* switch-case

Although the syntax differs between languages, the core logic is the same.

### The `if` Statement

The `if` statement executes a block of code only if a specified condition is
true.

```text
if condition then
    statement(s)
```

For example, in C, C++, C#, and Java, if you want check if `x` is greater than
`0` the conditional statement can be written as:

```csharp
int x = 5;
if (x > 0) {
    // ...
}
```

### The `if-else` Statement

The if-else statement executes one block of code if the condition is true, and
another block if it is false.

```text
if condition then
    statement(s)
else
    statement(s)
```

For example, in C, C++, C#, and Java, if you want check if `x` is greater than
`0` or not greater than `0`, the conditional statement can be written as:

```csharp
int x = 5;
if (x > 0) {
    // ...
} else {
    // ...
}
```

### The `switch-case` Statement

The `switch-case` statement is useful when comparing the same variable against
many possible values. It can be more readable than using many `if-else`
statements.

```text
switch expression do
    case value1:
        statement(s)
    case value2:
        statement(s)
    ...
    default:
        statement(s)
```

For example, in C, C++, C#, and Java, if you want to determine the name of the
day based on its ordinal number in the week, the conditional statement can be
written as:

```csharp
int day = 3;
string name = "";
switch (day) {
    case 1:
        name = "Monday";
        break;
    case 2:
        name = "Tuesday";
        break;
    case 3:
        name = "Wednesday";
        break;
    // ...
    default:
        name = "";
        break;
}
```

### Nesting conditions

Conditional statements can be placed inside other conditional statements - this
is called **nesting**. Nested conditions are useful when a decision depends on
the result of a previous decision. For example, you might first check if a user
is logged in, and then, inside that block, check if they have permission to
perform a certain action.

## Loops

In most modern programming languages, loops are usually implemented using one
of the following constructs:

* `for`,
* `while` (or `while-do`),
* `do-while` (or `repeat-until`),
* `foreach` (or `for-each`).

Although the syntax differs between languages, the core logic is the same.

### The `for` Loop

The `for` loop is used when the number of iterations is finite and
predetermined.

```text
for variable ← start to end do
    statement(s)
```

For example, in C, C++, C#, and Java, a `for` loop to iterate through numbers
from 0 to 9 can be written as:

```csharp
for (int i = 0; i <= 9; i++) {
    // ...
}
```

### The `while` Loop

The `while` (or `while-do`) loop is used when the number of iterations is
unknown in advance. The condition is checked before each iteration, so this
is called a **loop with a precondition**.

```text
while condition do
    statement(s)
```

For example, in C, C++, C#, and Java, a `while` loop to iterate through numbers
from 0 to 9 can be written as:

```csharp
int i = 0;
while (i <= 9) {
    // ...
    i++;
}
```

### The `do-while` Loop

The `do-while` (or `repeat-until`) loop also supports an unknown number of
iterations, but the condition is checked after each iteration. This is called a
**loop with a postcondition**, and it always executes at least once.

```text
repeat
    statement(s)
until condition
```

For example, in C, C++, C#, and Java, a `do-while` loop to iterate through
numbers from 0 to 9 can be written as:

```csharp
int i = 0;
do {
    // ...
    i++;
} while (i <= 9);
```

### The `foreach` Loop

The `foreach` (or `for-each`) loop is used to iterate over all elements in a
collection or array. It simplifies iteration when you don’t need to know the
index.

```text
for-each element in collection do
    statement(s)
```

For example, a `for-each` loop to iterate through array `nums` can be written
in C++ as:

```cpp
int nums[] = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
for (int i : nums) {
    // ...
}
```

...or in C# as...

```csharp
int[] nums = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
foreach (int i in nums) {
    // ...
}  
```

...or in Java as:

```java
int[] nums = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
for (int i : nums) {
    // ...
}   
```

### Nesting loops

Loops can also be nested, meaning that one loop is placed inside another. This
is common when working with multi-dimensional data, such as traversing rows and
columns in a matrix or iterating over a grid in a game. Furthermore, loops and
conditions can be freely combined — for example, a loop may contain an `if`
statement to process only certain elements, or an `if` statement may contain a
loop to perform repeated actions when a condition is true. This ability to mix
and nest loops and conditions allows for the creation of complex algorithms
while keeping the underlying logic structured.
