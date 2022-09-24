# Challenge 14: First Grep

## Description

Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/495d43ee4a2b9f345a4307d053b4d88d/file)?  This would be really tedious to look through manually, something tells me there is a better way.

### Tags

`picoCTF 2019` `General Skills`

### Points

`100`

## Solution

We need to find the flag in the file. We can do this by using the `grep` command. We can run the following command:

```bash
$ grep picoCTF file

picoCTF{grep_is_good_to_find_things_dba08a45}
```

## Flag

> picoCTF{grep_is_good_to_find_things_dba08a45}
