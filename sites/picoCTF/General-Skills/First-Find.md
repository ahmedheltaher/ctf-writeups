# Challenge 28: First Find

## Description

Unzip this archive and find the file named 'uber-secret.txt'

[Download zip file](https://artifacts.picoctf.net/c/551/files.zip)

### Tags

`picoGym Exclusive` `General Skills`

### Points

`100`

## Solution

This is a simple challenge. we just need to unzip the file and find the file named `uber-secret.txt`.

```bash
unzip files.zip
```

to unzip the file. and then we can find the file.

```bash
$ find ./ -name 'uber-secret.txt'

./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
```

we can see the file is in `./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt`
To get the flag, we can use `cat` to read the file.

```bash
$ cat ./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt

picoCTF{f1nd_15_f457_ab443fd1}
```

## Flag

> picoCTF{f1nd_15_f457_ab443fd1}
