# Challenge 5: Static ain't always noise

## Description

Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/0f6ea599582dcce7b4f1ba94e3617baf/static)? This [BASH script](https://mercury.picoctf.net/static/0f6ea599582dcce7b4f1ba94e3617baf/ltdis.sh) might help!

### Tags

`picoCTF 2021` `General Skills`

### Points

`20`

## Solution

We get a file called `static` and a bash script called `ltdis.sh`. The bash script is a script that uses `objdump` to disassemble the file. and `strings` to get the strings of the file. if we run the script, we get the following message:

```bash
$ chmod +x ltdis.sh

$ ./ltdis.sh static
```

After running the script, we will get 2 files: `static.ltdis.x86_64.txt` and `static.strings.txt`. lets cat the `static.strings.txt` file:

```bash
$ cat static.strings.txt
```

we will get a lot of strings. if we search for the flag, we will get the following message:

```bash
$ cat static.strings.txt | grep picoCTF

1020 picoCTF{d15a5m_t34s3r_6f8c8200}
```

as we can see, we got the flag.

## Flag

> picoCTF{d15a5m_t34s3r_6f8c8200}
