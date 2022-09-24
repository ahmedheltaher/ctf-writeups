# Challenge 16: convertme.py

## Description

Run the Python script and convert the given number from decimal to binary to get the flag. [Download Python script](https://artifacts.picoctf.net/c/30/convertme.py).

### Tags

`Beginner picoMini 2022` `General Skills` `base` `python`

### Points

`100`

## Solution

If we run the script, we get the following output:

```bash
$ python3 convertme.py

If 48 is in decimal base, what is it in binary base?
Answer: 

```

We need to convert the decimal number `48` to binary. We can do this in another terminal by using the `bin()` function in python. We can run the following command:

```bash
$ python3 -c "print(bin(48))"
0b110000
```

We can then enter the answer into the script:

```bash
$ python3 convertme.py

If 48 is in decimal base, what is it in binary base?
Answer: 110000

That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_762f748e}
```

Or we can take a look at the source code of the script:

```python
import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5f) + chr(0x05) + chr(0x08) + chr(0x2a) + chr(0x1c) + chr(0x5e) + chr(0x1e) + chr(0x1b) + chr(0x3b) + chr(0x17) + chr(0x51) + chr(0x5b) + chr(0x58) + chr(0x5c) + chr(0x3b) + chr(0x42) + chr(0x53) + chr(0x5c) + chr(0x0d) + chr(0x5e) + chr(0x50) + chr(0x4d) + chr(0x00) + chr(0x13)


num = random.choice(range(10,101))

print('If ' + str(num) + ' is in decimal base, what is it in binary base?')

ans = input('Answer: ')

try:
  ans_num = int(ans, base=2)
  
  if ans_num == num:
    flag = str_xor(flag_enc, 'enkidu')
    print('That is correct! Here\'s your flag: ' + flag)
  else:
    print(str(ans_num) + ' and ' + str(num) + ' are not equal.')
  
except ValueError:
  print('That isn\'t a binary number. Binary numbers contain only 1\'s and 0\'s')
```

as we can see, we can just hack our way through the script and get the flag:

```python
import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5f) + chr(0x05) + chr(0x08) + chr(0x2a) + chr(0x1c) + chr(0x5e) + chr(0x1e) + chr(0x1b) + chr(0x3b) + chr(0x17) + chr(0x51) + chr(0x5b) + chr(0x58) + chr(0x5c) + chr(0x3b) + chr(0x42) + chr(0x53) + chr(0x5c) + chr(0x0d) + chr(0x5e) + chr(0x50) + chr(0x4d) + chr(0x00) + chr(0x13)

flag = str_xor(flag_enc, 'enkidu')
print(flag)
```

Remember my friend, that you can always look at the source code of a script to get the flag. It's not always the best way to solve a challenge, but it's a good way to get the flag if you're stuck.

And Remember, we are HACKERS, not script kiddies. We don't need to follow the rules. 😉

## Flag

> picoCTF{4ll_y0ur_b4535_762f748e}
