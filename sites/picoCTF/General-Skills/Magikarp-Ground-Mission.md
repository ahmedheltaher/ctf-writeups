# Challenge 7: Magikarp Ground Mission

## Description

Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `a13b7f9d`

### Tags

`picoCTF 2021` `General Skills`

### Points

`30`

## Solution

We need to connect to the server using ssh. We need to lunch the instance first. after that, we can connect to the server using the following command:

```bash
$ ssh ctf-player@venus.picoctf.net -p 57496
```

when we connect to the server, after we run the `ls` command, we will get the following message:

```bash
$ ls

1of3.flag.txt  instructions-to-2of3.txt
```

we can see that there is a file called `1of3.flag.txt`. we can read the file using the `cat` command:

```bash
$ cat 1of3.flag.txt

picoCTF{xxsh_
```
if we cat the `instructions-to-2of3.txt` file, we will get the following message:

```bash
$ cat instructions-to-2of3.txt

Next, go to the root of all things, more succinctly `/`
```

we can see that we need to go to the root directory. we can do this by running the following command:

```bash
$ cd /
```

after we run the `ls` command, we will get the following message:

```bash
$ ls

2of3.flag.txt  boot  etc   instructions-to-3of3.txt  lib64  mnt  proc  run   srv  tmp  var
bin            dev   home  lib                       media  opt  root  sbin  sys  usr
```

we can see that there is a file called `2of3.flag.txt`. we can read the file using the `cat` command:

```bash
$ cat 2of3.flag.txt

0ut_0f_\/\/4t3r_
```

if we cat the `instructions-to-3of3.txt` file, we will get the following message:

```bash
$ cat instructions-to-3of3.txt

Lastly, ctf-player, go home... more succinctly `~`
```

we can see that we need to go to the home directory. we can do this by running the following command:

```bash
$ cd ~
```

after we run the `ls` command, we will get the following message:

```bash
$ ls

3of3.flag.txt drop-in
```

we can see that there is a file called `3of3.flag.txt`. we can read the file using the `cat` command:

```bash
$ cat 3of3.flag.txt

71be5264}
```

as we can see, we got the flag.

## Flag

> picoCTF{xxsh_0ut_0f_\/\/4t3r_71be5264}
