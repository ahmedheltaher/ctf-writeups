# Challenge 17: fixme1.py

## Description

Fix the syntax error in this Python script to print the flag. [Download Python script](https://artifacts.picoctf.net/c/38/fixme1.py).

### Tags

`Beginner picoMini 2022` `General Skills` `python`

### Points

`100`

## Solution

If we run the script, we get the following output:

```bash
$ python3 fixme1.py
File "/home/kali/Desktop/ctf/picoCTF/General-Skills/fixme1.py/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
```

We can see that there is an indentation error on line 20. We can fix this by removing the extra space on line 20. We can then run the script again:

```bash
$ python3 fixme1.py

That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_09ee727a}
```

Remember that indentation is important in Python.

## Flag

> picoCTF{1nd3nt1ty_cr1515_09ee727a}