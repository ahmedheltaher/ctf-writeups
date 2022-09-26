# Challenge 25: PW Crack 5

## Description

Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/79/level5.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/79/level5.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/79/level5.hash.bin) in the same directory too. Here's a [dictionary](https://artifacts.picoctf.net/c/79/dictionary.txt) with all possible passwords based on the password conventions we've seen so far.

### Tags

`Beginner picoMini 2022` `General Skills` `password_cracking` `hashing`

### Points

`100`

## Solution

This challenge is similar to the [previous one](./PW-Crack-4.md). We are given a script and an encrypted flag. also we are given a hash file. but this time we are given a dictionary file that contains lots of possible passwords.

We can use the same script to check the passwords. but this time we need to check all the passwords in the dictionary file.

```python
import hashlib

correct_pw_hash = open('level5.hash.bin', 'rb').read()

def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()

pos_pw_list = open('dictionary.txt', 'r').read().splitlines()

for pw in pos_pw_list:
    if hash_pw(pw) == correct_pw_hash:
        print("The password is: " + pw)
        break
```

if we run the script we will get the password.

```bash
$ python3 crack.py
The password is: 9581
```

Now we can use the password to decrypt the flag.

```bash
$ python3 level5.py
Please enter correct password for flag: 9581

Welcome back... your flag, user:
picoCTF{h45h_sl1ng1ng_36e992a6}
```

## Flag

> picoCTF{h45h_sl1ng1ng_36e992a6}
