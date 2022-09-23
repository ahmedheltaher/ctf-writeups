# Challenge 2: Python Wrangling

## Description

Python scripts are invoked kind of like programs in the Terminal... Can you run [this Python script](https://mercury.picoctf.net/static/325a52d249be0bd3811421eacd2c877a/ende.py) using [this password](https://mercury.picoctf.net/static/325a52d249be0bd3811421eacd2c877a/pw.txt) to get [the flag](https://mercury.picoctf.net/static/325a52d249be0bd3811421eacd2c877a/flag.txt.en)?

### Tags

`picoCTF 2021` `General Skills`

### Points

`10`

## Solution

We go 3 files in this challenge: `ende.py`, `flag.txt.en` and `pw.txt`. The first file is a python script that takes a password as an argument and decrypts the flag. The second file is the flag encrypted with the script. The third file is the password to decrypt the flag.

If we run the script with no arguments, we get the following message:

```bash
$ python3 ende.py
Usage: ende.py (-e/-d) [file]
```

as we can see, the script takes 2 arguments: the first one is `-e` or `-d` to encrypt or decrypt the file, and the second one is the file to encrypt or decrypt. If we run the script with the `-d` argument and the `flag.txt.en` file, we get the following message:

```bash
$ python3 ende.py -d flag.txt.en
Enter password: 
```

as we can see, the script asks for a password. If we enter the password in the `pw.txt` file (we can get it by running `cat pw.txt`), we get the following message:

```bash
$ python3 ende.py -d flag.txt.en
Enter password: ac9bd0ffac9bd0ffac9bd0ffac9bd0ff

picoCTF{4p0110_1n_7h3_h0us3_ac9bd0ff}
```

as we can see, the script decrypts the flag.

## Flag

> picoCTF{4p0110_1n_7h3_h0us3_ac9bd0ff}
