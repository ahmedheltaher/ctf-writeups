# Challenge 19: Glitch Cat

## Description

Our flag printing service has started glitching!\
`$ nc saturn.picoctf.net 53933`

### Tags

`Beginner picoMini 2022` `General Skills` `nc` `shell` `python`

### Points

`100`

## Solution

If we connect to the server, we get the following output:

```bash
$ nc saturn.picoctf.net 53933

'picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}'
```

We can see that the flag is being printed, but there are some characters missing. We can fix this by replacing the `chr()` function with the actual characters. We can use the `python3` command to do this:

```python
>>> print('picoCTF{gl17ch_m3_n07_' + chr(0x61) + chr(0x34) + chr(0x33) + chr(0x39) + chr(0x32) + chr(0x64) + chr(0x32) + chr(0x65) + '}')

'picoCTF{gl17ch_m3_n07_a4392d2e}'
```

## Flag

> picoCTF{gl17ch_m3_n07_a4392d2e}
