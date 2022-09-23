# Challenge 3: Wave a flag

## Description

Can you invoke help flags for a tool or binary? This program has extraordinarily helpful information...

### Tags

`picoCTF 2021` `General Skills`

### Points

`10`

## Solution

we get a file called `warm` that is a binary file. we need to make it executable by running `chmod +x warm`. if we run the file, we get the following message:

```bash
$ ./warm
Hello user! Pass me a -h to learn what I can do!
```

as we can see, the file takes the `-h` argument to show the help message. if we run the file with the `-h` argument, we get the following message:

```bash
$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_f0668f62}
```

as we can see, the file shows the flag.

## Flag

> picoCTF{b1scu1ts_4nd_gr4vy_f0668f62}
