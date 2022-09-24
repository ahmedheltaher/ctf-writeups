# Challenge 20: HashingJobApp

## Description

If you want to hash with the best, beat this test!\
`$ nc saturn.picoctf.net 63116`

### Tags

`Beginner picoMini 2022` `General Skills` `hashing` `nc` `shell` `python`

### Points

`100`

## Solution

If we connect to the server, we get the following output:

```bash
$ nc saturn.picoctf.net 63116

lease md5 hash the text between quotes, excluding the quotes: 'Microsoft'
Answer: 
```

We can see that we need to hash the text between the quotes. We can use the `python3` command to do this:

Note that the word is different each time.

```python

>>> import hashlib
>>> hashlib.md5('Microsoft'.encode()).hexdigest()
'140864078aeca1c7c35b4beb33c53c34'

```

Or we can use th `md5sum` command:

```bash
$ echo -n 'Microsoft' | md5sum

140864078aeca1c7c35b4beb33c53c34  -
```

We can then enter the hash into the server. it will then ask us to hash another word. We can repeat this process until we get the flag.

## Flag

> picoCTF{4ppl1c4710n_r3c31v3d_bf2ceb02}
