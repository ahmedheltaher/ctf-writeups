# Challenge 32: mus1c

## Description

I wrote you a [song](https://jupiter.challenges.picoctf.org/static/c594d8d915de0129d92b4c41e25a2313/lyrics.txt). Put it in the picoCTF{} flag format.

### Tags

`picoCTF 2019` `General Skills`

### Points

`300`

## Solution

In this challenge, we are given a file named `lyrics.txt`. we can use `cat` to read the file.

```bash
$ cat lyrics.txt

Pico's a CTFFFFFFF
my mind is waitin
It's waitin

Put my mind of Pico into This
my flag is not found
put This into my flag
put my flag into Pico


shout Pico
shout Pico
shout Pico

My song's something
put Pico into This

Knock This down, down, down
put This into CTF

shout CTF
my lyric is nothing
Put This without my song into my lyric
Knock my lyric down, down, down

shout my lyric

Put my lyric into This
Put my song with This into my lyric
Knock my lyric down

shout my lyric

Build my lyric up, up ,up

shout my lyric
shout Pico
shout It

Pico CTF is fun
security is important
Fun is fun
Put security with fun into Pico CTF
Build Fun up
shout fun times Pico CTF
put fun times Pico CTF into my song

build it up

shout it
shout it

build it up, up
shout it
shout Pico
```

We can see the file is a song. nothing special.

If we took a look at the hints, we can see the hint is `Do you think you can master rockstar?`.

If we google `rockstar`, we can see it is a programming language. we can use the [online interpreter](https://codewithrockstar.com/online) to run the code.

After we run the code, we can see the output:

```text
114
114
114
111
99
107
110
114
110
48
49
49
51
114
```

We can see the output is a bunch of numbers. we can python to convert the numbers to ascii.

```python

>>> ''.join([chr(int(i)) for i in '114 114 114 111 99 107 110 114 110 48 49 49 51 114'.split()])
'rrrocknrn0113r'
```

We can see the output is `rrrocknrn0113r`. lets try to put it in the flag format.

## Flag

> picoCTF{rrrocknrn0113r}
