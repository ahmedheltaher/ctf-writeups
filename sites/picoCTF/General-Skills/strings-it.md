# Challenge 12: strings it

## Description

Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/5bd86036f013ac3b9c958499adf3e2e2/strings)
without running it?

### Tags

`picoCTF 2019` `General Skills`

### Points

`100`

## Solution

We need to find the flag in the file without running it. We can do this by using the `strings` command. We can run the following command:

```bash
$ strings strings | grep picoCTF

picoCTF{5tRIng5_1T_827aee91}
```

## Flag

> picoCTF{5tRIng5_1T_827aee91}
