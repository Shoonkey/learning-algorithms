# BigInt

Sometimes it is necessary to store integers larger than the limits provided by the primitive data types. Then comes in BigInt, which is an implementation of numbers as, for example, an array of its digits or the number in base 2^31 - 1, along with all common operators.

In Python, for example, bigints are supported out of the box and numbers that surpass natural primitive limits are transformed into BigInts automatically under the hood. C++ has libs that provide implementations of it but it's not implemented in its standard.

Using BitInt we can calculate things for arbitrarily large numbers, as under the hood they're stored as an array of digits in an arbitrary base. Things like factorials, fibonacci numbers, etc.