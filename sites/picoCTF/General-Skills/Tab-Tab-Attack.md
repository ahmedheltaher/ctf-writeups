# Challenge 6: Tab, Tab, Attack

## Description

Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/9689f2b453ad5daeb73ca7534e4d1521/Addadshashanammu.zip)

### Tags

`picoCTF 2021` `General Skills`

### Points

`20`

## Solution

We get a zip file called `Addadshashanammu.zip`. If we unzip the file, using the command `unzip Addadshashanammu.zip`, we will get a directory called `Addadshashanammu`. If we `cd` into the directory, we will find another long named directory, we can write cd and then press tab to autocomplete the directory name. and we will keep doing this until we get to the flag file. the flag file is called `fang-of-haynekhtnamet`. if we cat the file, we will get some random gibberish. so we can use the command `strings fang-of-haynekhtnamet` to get the flag. with the command `grep` we can search for the flag. the flag is in the 3rd line.

```bash
strings fang-of-haynekhtnamet | grep picoCTF
```

## Flag

> picoCTF{l3v3l_up!_t4k3_4_r35t!_2bcfb2ab}
