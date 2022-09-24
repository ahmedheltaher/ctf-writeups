# Challenge 9: Warmed Up

## Description

What is 0x3D (base 16) in decimal (base 10)?

### Tags

`picoCTF 2019` `General Skills`

### Points

`50`

## Solution

We need to convert the hexadecimal number `0x3D` to decimal. We can do this by using the `int()` function in python. We can run the following command:

```bash
$ python3 -c "print(int('0x3D', 16))"

61
```

## Flag

> picoCTF{61}
