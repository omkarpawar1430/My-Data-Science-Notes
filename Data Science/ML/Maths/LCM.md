
Tags: #maths

------------------------------------------
LCM (Least Common Multiple) is the smallest positive integer that is divisible by two or more integers without leaving a remainder. To calculate the LCM of two numbers, we can use the formula:

> LCM(a, b) = (a * b) / GCD(a, b)

where GCD is the Greatest Common Divisor of the two numbers.

Here's the Python code to calculate the LCM of two numbers without using any library:

```python
def gcd(a, b):
    """
    Returns the GCD of two integers a and b using the Euclidean algorithm.
    """
    if b == 0:
        return a
    else:
        return gcd(b, a % b)

def lcm(a, b):
    """
    Returns the LCM of two integers a and b.
    """
    return (a * b) // gcd(a, b)

# Example usage
print(lcm(12, 24))  # Output: 24

```

---------------------
#### links:
[[]]
[[]]













---------------------
#### links:
[[]]
[[]]