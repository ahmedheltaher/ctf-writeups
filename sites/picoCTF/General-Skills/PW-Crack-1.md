# Challenge 21: PW Crack 1

## Description

Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/51/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/51/level1.flag.txt.enc) in the same directory too.

### Tags

`Beginner picoMini 2022` `General Skills` `password_cracking`

## Points

`100`

## Solution

In this challenge we are given a script and an encrypted flag. The script is a simple password checker, if we entered the correct password it will print the flag. we can take a look at the script. It might has something useful to us.

```python
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################


flag_enc = open('level1.flag.txt.enc', 'rb').read()



def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "691d"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_1_pw_check()
```

As we can see, the password is `691d` and it will be used to decrypt the flag.

let's run the script and enter the password.

```bash
$ python3 level1.py
Please enter correct password for flag: 691d

Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_56891419}
```

and this is why we don't store passwords in plain text.

## Flag

> picoCTF{545h_r1ng1ng_56891419}
