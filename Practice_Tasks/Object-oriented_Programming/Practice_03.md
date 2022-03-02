Object-oriented Programming, Practice #3
========================================

## Developer Tools

* [Eclipse Temurin JDK 17](https://adoptium.net)
* [IntelliJ IDEA](https://www.jetbrains.com/idea/download)
* [Git](https://git-scm.com)

## Problem #1: "Calculator of Rational Numbers" (2%)

Create application which can help users to do arithmetic operations (addition,
subtraction, multiplication, division, comparisons) with rational numbers. User
enters a first rational, an operator (+, -, *, /, <, >, =, !=, <=, >=), a second
rational and, after that, the application prints the result:

### Example

```
Calculator of Rational Numbers
(press Ctrl-Z/D to exit)

First rational: 1/2
Operator: +
Second rational: 2/3
Result: 1/2 + 2/3 = 7/6

First rational: 1/2
Operator: >
Second rational: 2/3
Result: 1/2 > 2/3: false

First rational: one
Error: Can't parse 'one' as input.

First rational: 1/0
Error: The denominator can't be equal to zero.

First rational: 1/2
Operator: 42
Error: '42' is not a valid operator.

First rational: ^Z
```

Your application has to check all the data it gets from the user carefully and
in cases of incorrect user input it has to print appropriate error messages.
User should be able to stop the application by pressing the Ctrl-Z (or Ctrl-D in
Linux) key combination.

In this program you have to develop a class Rational to represent rational
numbers.  Objects of this class (variables of this type) must support the
following methods:

| Method                                   | Meaning                                                                                                      |
| ---------------------------------------: | :----------------------------------------------------------------------------------------------------------- |
| Rational(int numerator, int denominator) | Creates a rational number. Throws an Exception if `den` is equal to 0.                                       |
| Rational add(Rational other)             | Returns the result of addition                                                                               |
| Rational subtract(Rational other)        | Returns the result of subtraction                                                                            |
| Rational multiply(Rational other)        | Returns the result of multiplication                                                                         |
| Rational divide(Rational other)          | Returns the result of division                                                                               |
| int compareTo(Rational other)            | Returns any negative integer if a < b, returns any positive if a > b, returns 0 if both are equal            |
| String toString()                        | Returns a string representatin in the format `numerator/denominator`                                         |
| static Rational parseRational(String s)  | Creates a new rational number from string. Throws Exceptions if the string does not contain a valid rational |

Objects of class Rational must be always in reduced form. Keep the sign of the
number in its numerator. Develop inner (private) methods to reduce rationals and
to find the greatest common divisor of numerator and denominator. Try to also
check all possible errors in the user's input

Use the Euclidean Algorithm to find the GCD:

```
function gcd(a, b)
    while b ≠ 0
        t := b
        b := a mod b
        a := t
    return a
```

## Problem #2: "BigInteger Rational" (2%)

Create a version of the Rational class that supports computations with
arbitrary precision numbers (Use the class `java.math.BigInteger`).