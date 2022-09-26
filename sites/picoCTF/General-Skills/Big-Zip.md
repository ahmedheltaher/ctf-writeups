# Challenge 29: Big Zip

## Description

Unzip this archive and find the flag.

[Download zip file](https://artifacts.picoctf.net/c/554/big-zip-files.zip)

### Tags

`picoGym Exclusive` `General Skills`

### Points

`100`

## Solution

If we unzip the file, we can see there are many files in the folder. If we tried to find the flag, we will find there no named `flag` or `picocTF` in the folder. So we need to use `grep` to find the flag.

```bash
$ grep -r "picoCTF" .

big-zip-files/folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}

```

we can see the flag is in `big-zip-files/folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt`

## Flag

> picoCTF{gr3p_15_m4g1c_ef8790dc}
