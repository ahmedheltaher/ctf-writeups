# Challenge 13: bases

## Description

What does this bDNhcm5fdGgzX3IwcDM1 mean? I think it has something to do with bases.

### Tags

`picoCTF 2019` `General Skills`

### Points

`100`

## Solution

We need to decode the string `bDNhcm5fdGgzX3IwcDM1`. We can do this by using the `base64` command. We can run the following command:

```bash
$ echo "bDNhcm5fdGgzX3IwcDM1" | base64 -d

l3arn_th3_r0p35
```

## Flag

> picoCTF{l3arn_th3_r0p35}
