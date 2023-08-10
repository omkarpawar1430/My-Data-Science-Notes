
Tags: #maths 

------------------------------------------
The greatest common divisor (GCD) of two or more integers is the largest positive integer that divides each of the integers without a remainder. For example, the GCD of 12 and 18 is 6, because 6 is the largest positive integer that divides both 12 and 18 without a remainder.

> HCF stands for Highest Common Factor, which is also known as Greatest Common Divisor (GCD).

To find the GCD of two integers, we can use the Euclidean algorithm, which is based on the fact that the GCD of two integers is the same as the GCD of one of the integers and the remainder of that integer divided by the other integer.

Here's how the algorithm works:

1.  We start with two integers, a and b.
2.  We divide a by b, and let r be the remainder.
3.  If r is 0, then b is the GCD of a and b.
4.  Otherwise, we set a = b and b = r, and go back to step 2.

For example, let's find the GCD of 12 and 18 using the Euclidean algorithm:

1.  We start with a = 12 and b = 18.
2.  We divide 18 into 12, and get a quotient of 0 and a remainder of 12. So r = 12.
3.  Since r is not 0, we set a = 18 and b = 12, and go back to step 2.
4.  We divide 12 into 18, and get a quotient of 1 and a remainder of 6. So r = 6.
5.  Since r is not 0, we set a = 12 and b = 6, and go back to step 2.
6.  We divide 6 into 12, and get a quotient of 2 and a remainder of 0. So r = 0.
7.  Since r is 0, we know that the GCD of 12 and 18 is 6.

Now let's see how we can implement this algorithm in Python:

```python
def gcd(a, b):
    while b != 0:
        r = a % b
        a = b
        b = r
    return a

```



---------------------
#### links:
[[]]
[[]]