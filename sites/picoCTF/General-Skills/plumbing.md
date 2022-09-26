# Challenge 31: plumbing

## Description

Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 7480`.

### Tags

`picoCTF 2019` `General Skills`

### Points

`200`

## Solution

When we connect to the server, we can see the server will send a ton of text to us. we can use `grep` to search for the flag.

```bash
$ nc jupiter.challenges.picoctf.org 7480 | grep picoCTF

picoCTF{digital_plumb3r_06e9d954}
```

## Flag

> picoCTF{digital_plumb3r_06e9d954}
