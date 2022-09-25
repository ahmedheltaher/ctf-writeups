# Challenge 15: Codebook

## Description

Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/101/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/101/codebook.txt)

### Tags

`Beginner picoMini 2022` `General Skills` `shell` `python`

### Points

`100`

## Solution

We need to run the python script `code.py` in the same directory as `codebook.txt`. We can do this by running the following command:

```bash
$ python3 code.py

picoCTF{c0d3b00k_455157_7d102d7a}
```

As we can see, we immediately got the flag. we can read the python script to see how it works.

```python
import random
import sys



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x13) + chr(0x01) + chr(0x17) + chr(0x07) + chr(0x2c) + chr(0x3a) + chr(0x2f) + chr(0x1a) + chr(0x0d) + chr(0x53) + chr(0x0c) + chr(0x47) + chr(0x0a) + chr(0x5f) + chr(0x5e) + chr(0x02) + chr(0x3e) + chr(0x5a) + chr(0x56) + chr(0x5d) + chr(0x45) + chr(0x5d) + chr(0x58) + chr(0x31) + chr(0x5e) + chr(0x05) + chr(0x5f) + chr(0x53) + chr(0x5a) + chr(0x10) + chr(0x5f) + chr(0x0e) + chr(0x13)



def print_flag():
  try:
    codebook = open('codebook.txt', 'r').read()
    
    password = codebook[4] + codebook[14] + codebook[13] + codebook[14] +\
               codebook[23]+ codebook[25] + codebook[16] + codebook[0]  +\
               codebook[25]
               
    flag = str_xor(flag_enc, password)
    print(flag)
  except FileNotFoundError:
    print('Couldn\'t find codebook.txt. Did you download that file into the same directory as this script?')



def main():
  print_flag()



if __name__ == "__main__":
  main()
```

We can see that the flag is encrypted with a password. The password is the 4th, 14th, 13th, 14th, 23rd, 25th, 16th, 0th, and 25th characters of the `codebook.txt` file. We can get the password by copying the codebook and password line into a python shell and running the following code:

```python
>>> codebook = 'azbycxdwevfugthsirjqkplomn'

>>> password = codebook[4] + codebook[14] + codebook[13] + codebook[14] +\
               codebook[23]+ codebook[25] + codebook[16] + codebook[0]  +\
               codebook[25]

>> password
'chthonian'
```

So we can see that the password is `chthonian`. We can also try to read the flag_enc variable to see what it is.

```python
>>> flag_enc = chr(0x13) + chr(0x01) + chr(0x17) + chr(0x07) + chr(0x2c) + chr(0x3a) + chr(0x2f) + chr(0x1a) + chr(0x0d) + chr(0x53) + chr(0x0c) + chr(0x47) + chr(0x0a) + chr(0x5f) + chr(0x5e) + chr(0x02) + chr(0x3e) + chr(0x5a) + chr(0x56) + chr(0x5d) + chr(0x45) + chr(0x5d) + chr(0x58) + chr(0x31) + chr(0x5e) + chr(0x05) + chr(0x5f) + chr(0x53) + chr(0x5a) + chr(0x10) + chr(0x5f) + chr(0x0e) + chr(0x13)

>>> flag_enc
'\x13\x01\x17\x07,:/\x1a\rS\x0cG\n_^\x02>ZV]E]X1^\x05_SZ\x10_\x0e\x13'
```

The way that the flag is encrypted is by using the `str_xor` function. The `str_xor` function takes in two strings and returns the xor of the two strings. We can see that the `str_xor` function is called with the `flag_enc` variable and the `password` variable.

First it extends the password to the length of the flag_enc variable. Then it returns the xor of the two strings.

And that is how we get the flag.

## Flag

> picoCTF{c0d3b00k_455157_7d102d7a}
