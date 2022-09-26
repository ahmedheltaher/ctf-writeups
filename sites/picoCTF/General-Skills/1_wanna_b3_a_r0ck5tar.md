# Challenge 34: 1_wanna_b3_a_r0ck5tar

## Description

I wrote you another [song](https://jupiter.challenges.picoctf.org/static/b99c57e4274172bf3c93534b6d59632d/lyrics.txt). Put the flag in the picoCTF{} flag format

### Tags

`picoCTF 2019` `General Skills`

### Points

`350`

## Solution

This challenge is a follow up of [mus1c](./mus1c.md) challenge. In this challenge, we are given a file named `lyrics.txt`. we can use `cat` to read the file.

If we try to run the code in the online interpreter, we will get the following error:

```text
Rock is electric heaven
       ^
Expected [A-ZÀÁÂÃÄÅÆÇÈÉÊËÌÍÎÏÐÑÒÓÔÕÖØÙÚÛÜÝÞĀĂĄĆĈĊČĎĐĒĔĖĘĚĜĞĠĢĤĦĨĪĬĮİĲĴĶĸĹĻĽĿŁŃŅŇŊŌŎŐŒŔŖŘŚŜŞŠŢŤŦŨŪŬŮŰŲŴŶŸŹŻŽ] or [a-zàáâãäåæçèéêëìíîïðñòóôõöøùúûüýþāăąćĉċčďđēĕėęěĝğġģĥħĩīĭįıĳĵķĸĺļľŀłńņňŋōŏőœŕŗřśŝşšţťŧũūŭůűųŵŷÿźżžŉß] but " " found.
line 21 col 8
```

So we Cannot run the code in the online interpreter. But if we do a little bit of research, we will find that the Rockstar programming language has compilers for many languages. We can use the [Rockstar compiler](https://github.com/yyyyyyyan/rockstar-py) to compile the code to python.

After installing the compiler, we can run the following command to compile the code:

```bash
rockstar-py -i lyrics.txt -o lyrics.py
```

We will get the following python code:

```python
Rocknroll = True
Silence = False
a_guitar = 10
Tommy = 44
Music = 170
the_music = input()
if the_music == a_guitar:
    print("Keep on rocking!")
    the_rhythm = input()
    if the_rhythm - Music == False:
        Tommy = 66
        print(Tommy!)
        Music = 79
        Jamming = 78
        print(Music!)
        print(Jamming!)
        Tommy = 74
        print(Tommy!)
        They are dazzled audiences
        print(it!)
        Rock = 86
        print(it!)
        Tommy = 73
        print(it!)
        break
        print("Bring on the rock!")
        Else print("That ain't it, Chief")
        break
```

We Can See the code is not valid python code. and we cannot run it, if we try to under stand it we will find that it is a simple code that will print some numbers but if we noticed the code we will find a comment that says `They are dazzled audiences` If we know try to run the following code, in the online interpreter

```text
They are dazzled audiences
shout They
```

we will get this output:

```text
79
```

So we can see that the code is trying to print the ASCII value of the string `They are dazzled audiences`.

So we got all the numbers that the code is trying to print. So we can use the following python code to get the flag:

```python
>>> ''.join([chr(int(i)) for i in '66 79 78 74 79 86 73'.split()])
'BONJOVI'
```

So lets put the flag in the picoCTF{} flag format

## Flag

> picoCTF{BONJOVI}
