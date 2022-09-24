# Challenge 8: Lets Warm Up

## Description

If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?

### Tags

`picoCTF 2021` `General Skills`

### Points

`50`

## Solution

We need to convert the hexadecimal number `0x70` to ASCII. We can do this by using the `chr()` function in python. We can run the following command:

```bash
$ python3 -c "print(chr(0x70))"

p
```

## Flag

> picoCTF{p}