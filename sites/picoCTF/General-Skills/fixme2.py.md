# Challenge 18: fixme2.py

## Description

Fix the syntax error in the Python script to print the flag. [Download Python script](https://artifacts.picoctf.net/c/67/fixme2.py).

### Tags

`Beginner picoMini 2022` `General Skills` `python`

### Points

`100`

## Solution

If we run the script, we get the following output:

```bash
$ python3 fixme2.py

  File "/home/kali/Desktop/ctf/picoCTF/General-Skills/fixme2.py/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
```

We can see that there is a syntax error on line 22. We can fix this by changing the `=` to `==`. We can then run the script again:

```bash
$ python3 fixme2.py

That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_f6a5aefc}
```

Remember that `=` is used for assignment and `==` is used for comparison.

## Flag

> picoCTF{3qu4l1ty_n0t_4551gnm3nt_f6a5aefc}
