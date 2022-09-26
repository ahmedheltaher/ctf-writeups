# Challenge 4: PW Crack 4

# Description

Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/60/level4.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/60/level4.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/60/level4.hash.bin) in the same directory too. There are 100 potential passwords with only 1 being correct. You can find these by examining the password checker script.

## Tags

`Beginner picoMini 2022` `General Skills` `password_cracking` `hashing`

## Points

`100`

## Solution

In this challenge we are given a script and an encrypted flag. also we are given a hash file. The script is a simple password checker, if we entered the correct password it will print the flag. if we take a look at the script. we will find it almost identical to the [previous challenge](./PW-Crack-3.md). the only difference is the number of potential passwords. we can use the same method to solve this challenge.

```python
import hashlib

correct_pw_hash = open('level4.hash.bin', 'rb').read()

def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()

pos_pw_list = ["8c86", "7692", "a519", "3e61", "7dd6", "8919", "aaea", "f34b", "d9a2", "39f7", "626b", "dc78", "2a98", "7a85", "cd15", "80fa", "8571", "2f8a", "2ca6", "7e6b", "9c52", "7423", "a42c", "7da0", "95ab", "7de8", "6537", "ba1e", "4fd4", "20a0", "8a28", "2801", "2c9a", "4eb1", "22a5", "c07b", "1f39", "72bd", "97e9", "affc", "4e41", "d039", "5d30", "d13f", "c264", "c8be", "2221", "37ea", "ca5f", "fa6b", "5ada", "607a", "e469", "5681", "e0a4", "60aa", "d8f8", "8f35", "9474", "be73", "ef80", "ea43", "9f9e", "77d7", "d766", "55a0", "dc2d", "a970", "df5d", "e747", "dc69", "cc89", "e59a", "4f68", "14ff", "7928", "36b9", "eac6", "5c87", "da48", "5c1d", "9f63", "8b30", "5534", "2434", "4a82", "d72c", "9b6b", "73c5", "1bcf", "c739", "6c31", "e138", "9e77", "ace1", "2ede", "32e0", "3694", "fc92", "a7e2"]

for pw in pos_pw_list:
    if hash_pw(pw) == correct_pw_hash:
        print("The password is: " + pw)
```

If we run the script we just wrote we will get the correct password. `607a`
We can run the script again to get the flag.

```bash
$ python3 level4.py
Please enter correct password for flag: 607a

Welcome back... your flag, user:
picoCTF{fl45h_5pr1ng1ng_d770d48c}
```

## Flag

> picoCTF{fl45h_5pr1ng1ng_d770d48c}