# Java Types & Expressions

## Intro

Programming languages are a combination of mathematical concepts from computer science and human language concepts such as syntax (grammar) and meaning (semantics). The key to understanding programming languages requires not just understanding the mathematical concepts but the grammar and semantics of the programming language.


## Idea of Types:

Types are basically the collection/grouping of values, usually specified by a set of possible values, a set of allowed operations on these values, and/or a representation of these values for an abstract or concrete/physical machine.


In Java, there's a few primitive/basic type families and their types:

**Integers** (types that represent whole numbers):
* `byte` - 8-bit integer that represents the integer range of [-128 , 127]
* `char` - 16-bit integer for representing characters from text.
* `short` - 16-bit integer that represents the integer range of [−32,768 , 32,767]
* `int` - 32-bit integer that represents the integer range of [−2,147,483,648 , 2,147,483,647]
* `long` - 64-bit integer that represents the integer range of [−9,223,372,036,854,775,808 , 9,223,372,036,854,775,807]

**Floating-Points** (types that (imperfectly) represent real numbers):
* `float` - 32-bit floating point type.
* `double` - 64-bit floating point type.

**Textual**:
* `String` - represents text, this isn't a primitive but it is a basic type. It's also an `Object` type.

**Special**:
* `boolean` - 8-bit value that represents two values: `true` and `false`.
* `void` - represents no return type for a method. Methods with `void` do not return any values after they complete their execution.
* `Object` - represents the most basic object. Java is Object-Oriented and all user-defined classes use `Object`. The purpose of CSC205 aka Object-Oriented Programming with Java, is to teach you about objects.

---

## Expressions

In programming languages and math, there's the concept of an _expression_. Expressions, in programming languages, are any line/part of code that can compute a value. Here are some examples that use the basic data types we talked about:

`2 * 2` -> This expression is the multiplication of two integers, the type of the expression will thus be an integer type result. The result of course will be an `int`.

`2 * 2.0` -> this expression is the multiplication of an integer (left) and a floating-point value (right), the type of the expression will be a floating-point result type and this is because mixing integers with floating-points, in an expression, are defined to result in a floating-point type. In this case, the `2` integer is converted to `2.0` then multiplied with the other `2.0`.

`a >= 5` -> this expression is a comparison (greater-than-or-equal to) between a variable and an integer, the expression will thus result as a boolean type since the only posibility is whether `a` is greater-than-or-equal to `5`.

Mixing data types where one type is larger in bits/bytes than the others usually results in an expression where the type is the largest sized data type. IE mixing `long` (64-bit) and `int` (32-bit) in an expression will give a result that is a `long` type.

`2 * 5 + b` -> this is a multi-expression (expression within expression). The expression (should) first compute the `2 * 5` and then compute the result of that value with `i`.
`(2 * 5) + b` -> same expression but nicely organized with parentheses.

`c` -> a variable by itself is considered a valid expression, the type of the expression is the type of the variable itself!

`"hi" + 1` -> a string added with a number (integer or floating-point) results in a string expression. The `1` is automatically converted from an `int` type into a `String` like "1" and then combined with "hi" to create `"hi1"`. This kind of automatic conversion is called **__implicit conversion__**.

`i + a.m()` -> expression where we have mathematic addition between a variable and a method call. This expression is only valid if `i` and the return value of the method `m` have compatible types. Typing rules, such as mixing integers and floating-point, still apply.

---

### Operators

In Java, expressions work on a basis of operators and how they're defined for various types.

For Java, there's different categories of operators:

* Arithmetic operators
* Bitwise operators
* Comparison operators
* Logical operators
* Assignment operators
* Special operators


#### Arithmetic Operators (example):

* `+` - addition (`x + y`)
* `-` - subtraction (`x - y`)
* `-` - negate (`-x`)
* `+` - int promotion (`+x`) [promotes an integer expression's type to an `int` type]
* `*` - multiplication (`x * y`)
* `/` - division (`x / y`)

* `%` - modulo/integer division-remainder (`x % y`) [gives integer remainder]
	```
	10 / 3 == 3
	10 % 3 == 1. Why?
	What's a multiple of 3 closest to 10? Answer: 9.
	What's 10 - 9? Answer: 1, thus the modulo of 10 with 3 is 1.
	
	26 % 9 == 8. Multiple of 9 closest to 26 is 18. 26 - 18 == 8.
	
	13 % 3 == 1, multiple of 3 closest to 13 is 12, so 13-12 == 1.
	9 % 3 == 0. multiple of 3 closest to 9 is 9, so 9 - 9 == 0.
	a % b == 0, if 'a' is a multiple of 'b'.
	```

* `++` - increment: increases a numeric value by 1 (`++x`) [pre: increases value first in expression] (x++) [post: increases value after expression]
* `--` - decrement: decreases a numeric value by 1 (`--x`) [pre: decreases value first in expression] (x--) [post: decreases value after expression]

#### Bitwise Operators (example) [gives an integer type result]

* `&` - bitwise AND (`x & y`)
* `|` - bitwise OR (`x | y`)
* `^` - bitwise XOR (`x ^ y`)
* `<<` - logical/arithmetic Left Bit Shift (`x << y`)
* `>>` - arithmetic Right Bit Shift (`x >> y`)
* `>>>` - logical Right Bit Shift (`x >>> y`)
* `~` - bitwise NOT/complement (`~x`)

#### Comparison Operators (example) [gives a boolean type result]

* `>` - Greater-Than (`x > y`)
* `>=` - Greater-Than-Or-Equal-To (`x >= y`)
* `<` - Less-Than (`x < y`)
* `<=` - Less-Than-Or-Equal-To (`x <= y`)
* `==` - Equal-To (`x == y`)
* `!=` - Not-Equal-To (`x != y`)
* `instanceof` - Instance of "class" (`x instanceof y`) [used to check if an object is from a specific class]

#### Logical Operators (example) [gives a boolean type result]

* `&&` - logical AND (`x && y`)
* `||` - logical OR (`x || y`)
* `!` - logical NOT (`!x`)

#### Assignment Operators (example)

* `=` - Assignment/Copy (`x = y`)
* `+=` - Compound Addition (`x += y`) [same as: (`x = x + y`)]
* `-=` - Compound Subtraction (`x -= y`) [same as: (`x = x - y`)]
* `*=` - Compound Multiplication (`x *= y`) [same as: (`x = x * y`)]
* `/=` - Compound Division (`x /= y`) [same as: (`x = x / y`)]
* `%=` - Compound Modulo (`x %= y`) [same as: (`x = x % y`)]
* `&=` - Compound Bitwise-AND (`x &= y`) [same as: (`x = x & y`)]
* `|=` - Compound Bitwise-OR (`x |= y`) [same as: (`x = x | y`)]
* `^=` - Compound Bitwise-XOR (`x ^= y`) [same as: (`x = x ^ y`)]
* `<<=` - Compound Left Bit Shift (`x <<= y`) [same as: (`x = x << y`)]
* `>>=` - Compound Arithmetic Right Bit Shift (`x >>= y`) [same as: (`x = x >> y`)]
* `>>>=` - Compound Logical Right Bit Shift (`x >>>= y`) [same as: (`x = x >>> y`)]

#### Special Operators (example)

* `.` - Field/Member Access (`x.y`)


### Operator Precedence

Similar to how math has PEMDAS/BODMAS to remember the precedence of each expression in math, Java and other programming languages also have their own defined operator precedence. Given that expressions can have inner expressions, it's important to know what operators and their operands are first processed your Java program runs.

The following table represents, from **highest** priority to **lowest** priority, what operators go first.

```
Level   Operator   Description           Associativity
------------------------------------------------------
16        ()       parentheses           left-to-right
          []       array access
          new      object creation
           .       member access
          ::       method reference
------------------------------------------------------
15        ++       unary post-increment  left-to-right
          --       unary post-decrement
------------------------------------------------------
14        +        unary plus            right-to-left
          -        unary minus
          !        unary logical NOT
          ~        unary bitwise NOT
          ++       unary pre-increment
          --       unary pre-decrement
------------------------------------------------------
13     (type)expr  type cast             right-to-left
------------------------------------------------------
12      * / %      multiplicative        left-to-right
------------------------------------------------------
11       + -       additive              left-to-right
          +        string concatenation
------------------------------------------------------
10     << >> >>>   shift                 left-to-right
------------------------------------------------------
9      < <= > >=   relational            left-to-right
       instanceof
------------------------------------------------------
8        == !=     equality              left-to-right
------------------------------------------------------
7         &        bitwise AND           left-to-right
------------------------------------------------------
6         ^        bitwise XOR           left-to-right
------------------------------------------------------
5         |        bitwise OR            left-to-right
------------------------------------------------------
4        &&        logical AND           left-to-right
------------------------------------------------------
3        ||        logical OR            left-to-right
------------------------------------------------------
2        ?:        ternary               right-to-left
------------------------------------------------------
1      = += -=     assignment            right-to-left
      *= /= %=
      &= ^= |=
     <<= >>= >>>=
------------------------------------------------------
```

so if we're given an expression like: `2 + 5 * 9 ^ 3 & 24 - 2 << 3`.

The result is of an `int` type with the value `47`.

The way Java and its Runtime has processed the number is as:
```java
2 + (5 * 9) ^ 3 & 24 - 2 << 3            // multiplication first.
(2 + (5 * 9)) ^ 3 & (24 - 2) << 3        // addition then subtraction done next.
(2 + (5 * 9)) ^ 3 & ((24 - 2) << 3)      // bit shift done next.
(2 + (5 * 9)) ^ (3 & ((24 - 2) << 3))    // the Bitwise-AND done next.
(2 + (5 * 9)) ^ (3 & ((24 - 2) << 3))    // then the Bitwise-XOR done last.
```


### Methods

Methods are for organizing code functionality and mapping it to a name.

Method Structure:
```
<zero or more modifiers> <return-type> <method name>(<comma-separated parameters>) <block statement>
```

Basic Modifiers that you can use on methods:
```java
public protected private static final
```

* `static` -> means the method is only tied to the class itself, not to any object of a class.
* `final` -> means the method cannot be overriden by subclasses (CSC205 will teach you what a subclass is).


The other modifiers are for controlling the visibility of methods (and class members).
Here's a table that explains the modifiers how much visibility they allow. 
```
✔️: accessible
❌: not accessible
-------------------------------------------------------------------------------------------
            |  Class  |  Package  |  Subclass(same pkg)  |  Subclass(diff pkg)  |  World  |
-------------------------------------------------------------------------------------------
public      |   ✔️    |    ✔️    |          ✔️          |          ✔️         |    ✔️   |
-------------------------------------------------------------------------------------------
protected   |   ✔️    |    ✔️    |          ✔️          |          ✔️         |    ❌️   |
-------------------------------------------------------------------------------------------
no modifier |   ✔️    |    ✔️    |          ✔️          |          ❌         |    ❌️   |
-------------------------------------------------------------------------------------------
private     |   ✔️    |    ❌️    |          ❌️          |          ❌         |    ❌️   |
-------------------------------------------------------------------------------------------
```

Example:
```java
public static int printGreeting(String name) {
	System.out.println("Hello " + name + ", I hope you're doing well!");
}
```

---

# Java Statements

Statements are any part/line of code that performs a basic computing action such as loading/storing data, managing control flow, or other things. Typically, statements can use expressions as part of their construct. Let's look at a few statements. Many statements also allow statements for them, allow for more intricate, complex code to accomplish more complex tasks.


## Block Statement:

Most basic statement that begins using curly brackets and contains statements between those curly brackets.
```java
{
	<statement1>;
	...
	<statementN>;
}
```

## Expression Statement:

Most common statement, usually method calls or data manipulation of variables, basically a statement that is solely an expression.
```
<expression>;
```


## Variable Declaration and Initialization Statement:

For basic data types:
```
<type-name> <variable name> = <expression that matches the type-name>;
```
Example:
```java
int i = 5;
```

For Arrays:
```
<type-name>[] <variable name> = new <type-name>[<integer expression>]{<comma-separated expressions that matches the type-name>};
```
Example:
```java
int[] i = new int[3]{5, 7, 100};
```

If you just want the array to start empty, omit the `{}` part:
```
<type-name>[] <variable name> = new <type-name>[<integer expression>];
```
Example:
```java
double[] nums = new double[a * 3];
```

For Objects:
```
<type-name> <variable name> = new <type-name>(<comma-separated values for constructor>);
```
Example:
```java
MyClass g = new MyClass();
```


## If-Statement:

Most basic control flow statement, runs code based on a boolean expression called a _condition_.
```
if (<boolean expression>) <statement>
```
Example:
```java
if( a > 5 ) {
	System.out.println("a > 5");
}
```

If an `else` portion exists, it will run if the condition is false.
```
if (<boolean expression>) <statement>
else <statement>
```
Example:
```java
if( (b & 1) != 0 ) {
	System.out.println("b is odd");
} else {
	System.out.println("b is even");
}
```

If an `else if` portion exists, it will run if the previous if-statement condition fails, running down as a cascade.
```
if (<boolean expression>) <statement>
else if (<boolean expression>) <statement>
```
Example:
```java
if( c >= 100 && c <= 200 ) {
	System.out.println("100 <= c <= 200");
} else if( c > 200 ) {
	System.out.println("c > 200");
}
```

If both `else if` and `else` portions exist, it will work as a cascade and the `else` part will only run if the `if` and all the `else if`s have failed.
```
if (<boolean expression>) <statement>
else if (<boolean expression>) <statement>
...
else <statement>
```
Example:
```java
if( grade >= 90 ) {
	System.out.println("grade: A");
} else if( grade >= 80 ) {
	System.out.println("grade: B");
} else if( grade >= 70 ) {
	System.out.println("grade: C");
} else if( grade >= 60 ) {
	System.out.println("grade: D");
} else {
	System.out.println("grade: F");
}
```

### Ternary Expression:

If you ever come across a situation where you have to initialize a variable to a value that's based on an existing condition, rather than making a variable and then using an if-statement, you can alternatively use a ternary expression aka an inline if-expression.

```
<boolean expression> ? <expression if true> : <expression if false>
```

Example:
```java
int i = (a > 5)? a * 5 : a + 5;
...
int x = ...;
System.out.println("is x greater than 7?: " + (x > 7? "yes" : "no"));
```

Since Ternary Expressions are themselves expressions, that means you can _nest_ them but be careful doing this because it can hurt readability [ability for programmers to read and understand what the code is doing and why]. A good tip is to use parentheses to make it a bit clearer but still tread carefully.
:
```java
int comparison = (x < 0)? -1 : ((x > 0)? 1 : 0);
```


## Switch-Statement:

More advanced, compact form of the if-statement.
Most useful if you have to compare a singular item to alot of different values.
You can have as many cases as you need, as long as there's no duplicate cases.
The `default` case is optional.
If you don't have a `break` separating each case, the code control-flow will then fall through into the code of the next case!
`break` pretty much stops the control flow from going into the next case's code.
`default` doesn't need a `break` since `default` case has to always be the ending case.
```
switch (<integer or string expression>) {
	case <integer or string constant expression>:
		<statement>
		break;
	default:
		<statement>
}
```
Example:
```java
switch( title ) {
	case "King": {
		System.out.println("Welcome your majesty!");
		break;
	}
	case "Queen": {
		System.out.println("Welcome your highness!");
		break;
	}
	case "Princess": {
		System.out.println("Greetings my princess!");
		break;
	}
	case "Prince": {
		System.out.println("Hello my prince!");
		break;
	}
	default: {
		System.out.println("Hello your grace.");
	}
}
```


## Loop Statements:

For loops, they will run a statement until the boolean expression, called a _controller_ or also called a _condition_, is `false`.

### While Loops:
```
while (<boolean expression>) <statement>
```

### Do-While Loops:
```
do <statement> while (<boolean expression>);
```

### For Loops:

For loops are complicated, but more compact.
There are 3 parts to a for-loop.
First part is variable declaration or initialization. Typically called the `init` portion.
Second part is the condition as a boolean expression, this part controls the loop.
Third part is the post expression which runs after the statement body of the for-loop has finished executing.
All 3 parts are optional
```
for ( <variable declaration/initialization> ; <boolean expression> ; <post expression> ) <statement>
```
A for-loop is equivalent to a broken up while-loop:
```
<variable declaration/initialization>;
while (<boolean expression>) {
	<statement>
	<post expression>;
}
```

For Arrays and other collection objects [special objects that hold multiple data in a similar manner to arrays], there is a special for-loop syntax that helps simplify iterating/traversing these kinds of objects:
```
for (<variable declaration that matches type of array/collection> : <array/collection typed expression>) <statement>
```
Example:
```java
int[] nums = new int[array_size];
fillNums(nums);
for (int num : nums) {
	System.out.println(num);
}
```

### Loop Controllers: Flow Statements
* **`continue`** -> skips the current iteration of the loop and goes to the next.
* **`break`** -> completely stops the loop.

**NOTE:** be careful using a switch statement in a loop because the `break` needed for the cases will NOT stop the loop.
If you have to stop the loop some how and you want a switch statement within the loop, use another variable, preferrably a `boolean` type, to be able to kill the loop. Your homework is figuring out how to do that!


## Return Statement:

Used in methods to return to its previous calling location and, if the method doesn't have a `void` return type, gives back a value.
```
return <expression that matches the return type of the method>
```

If the method has a `void` return type, then no expression is given to the `return`:
```
return;
```


## Try-Catch Statement:

The try-catch statement is for doing exception/error handling, allowing the program to "try" a block of code and "catch" any exceptions (errors) that may occur during execution. It's important to be able to handle errors as they happen to make the program more robust and continue running. Without handling exceptions/errors, a program would cease every time whether unexpectedly or the user is assaulted with an error message they might not understand.

At its most basic:
```
try <block statement>
catch (<exception type> <variable name>) <block statement>
```

You can have as many catch portions as you need to handle as many errors as needed.
```
try <block statement>
catch (<exception type> <variable name>) <block statement>
...
catch (<exception type> <variable name>) <block statement>
```

Also as an option, you can use a `finally` portion that will **always** execute regardless whether an error happened or not:
```
try <block statement>
catch (<exception type> <variable name>) <block statement>...
finally <block statement>
```

Example without try-catch:
```java
int[] myNumbers = {1, 2, 3};
System.out.println(myNumbers[10]); // error!
```
Console Message:
```
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: Index 10 out of bounds for length 3
```

Example _with_ try-catch:
```java
int[] myNumbers = {1, 2, 3};
try {
	System.out.println(myNumbers[10]);
} catch(ArrayIndexOutOfBoundsException e) {
	System.out.println("Error :: ****" + e + "**** | try a different index.");
}
```

Not exactly recommended but if it's necessary to catch ALL errors with one catch block, you can use the `Exception` type.
It's not recommended because sometimes different errors need to be handled differently but, if you're planning to handle all errors the same way, then simply using `Exception` is fine. Special errors I'd recommend handling specially are `NullPointerException` (trying to use an object that's null) and `ArithmeticException` (such as dividing by 0).
```
int[] myNumbers = {1, 2, 3};
try {
	System.out.println(myNumbers[10]);
} catch(Exception e) {
	System.out.println("Error :: ****" + e + "****");
}
```

---
