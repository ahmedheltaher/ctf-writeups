# Lesson 22: Memory Forensics

> Lesson Link:\
> *[https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/22-memory-forensics](https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/22-memory-forensics)*

## Introduction

Memory forensics is the process of examining computer memory to determine what programs have been run, what data has been accessed, and what other actions have occurred on a computer. Memory forensics is a type of digital forensics that is used to investigate computer memory. Memory forensics is used to determine what programs have been run, what data has been accessed, and what other actions have occurred on a computer.

## Challenge

> Name:\
> *Monaliza*

---

> Description:\
> *We cannot identify this suspicious user behavior, but we know he is a big fan of Monaliza*

## Solution

In this challenge, we are given a .7z file, which contains a .mem file.

if we try to run `file` on the file, we get the following output:

```bash
monaliza.mem: data
```

if we try to cat the file, we a lot of lines. so we might try to use `strings` with `grep` to search for the flag.

```bash
strings monaliza.mem | grep "Flag{"
```

We get the following output:

```bash
Flag{i_w!ll_d3l3t3_my_s3cret}
Flag{i_w!ll_d3l3t3_my_s3cret}
Flag{i_w!ll_d3l3t3_my_s3cret}
Flag{i_w!ll_d3l3t3_my_s3cret}
Flag{i_w!ll_d3l3t3_my_s3cret}
```

If we try to submit the flag, the server will tell us that the flag is wrong.

So We need a tool to analyze the memory dump.

We can use `volatility` for that.

We can install it using `pip`:

```bash
pip install volatility
```

We can use the following command to analyze the memory dump:

```bash
volatility -f monaliza.mem imageinfo
```

We get the following output:

```bash
Volatility Foundation Volatility Framework 2.6
INFO    : volatility.debug    : Determining profile based on KDBG search...
          Suggested Profile(s) : WinXPSP2x86, WinXPSP3x86 (Instantiated with WinXPSP2x86)
                     AS Layer1 : IA32PagedMemoryPae (Kernel AS)
                     AS Layer2 : FileAddressSpace (/home/kali/Downloads/monaliza.mem)
                      PAE type : PAE
                           DTB : 0xbd1000L
                          KDBG : 0x80545ce0L
          Number of Processors : 1
     Image Type (Service Pack) : 3
                KPCR for CPU 0 : 0xffdff000L
             KUSER_SHARED_DATA : 0xffdf0000L
           Image date and time : 2020-03-21 10:12:35 UTC+0000
     Image local date and time : 2020-03-21 03:12:35 -0700
```

We can see that the profile is `WinXPSP2x86`.

We can use the following command to get the processes:

```bash
volatility -f monaliza.mem --profile=WinXPSP2x86 pslist
```

We get the following output:

```bash
Volatility Foundation Volatility Framework 2.6
Offset(V)  Name                    PID   PPID   Thds     Hnds   Sess  Wow64 Start                          Exit
---------- -------------------- ------ ------ ------ -------- ------ ------ ------------------------------ ------------------------------
...
0x8201b3c0 mspaint.exe             800   1248      6      103      0      0 2020-03-21 10:10:29 UTC+0000                                 
...
```

We can see that the process `mspaint.exe` is running.

We can use the following command to get the process memory dump:

```bash
volatility -f monaliza.mem --profile=WinXPSP2x86 memdump -p 800 -D .
```

We get the following output:

```bash
Volatility Foundation Volatility Framework 2.6
Writing mspaint.exe [   800] to 800.dmp
```

we can see that the process memory dump is saved in the file `800.dmp`.

as we found at the beginning the file is a data file, so we can rename it to `800.data` to be able to open it in gimp. by running the following command:

```bash
mv 800.dmp 800.data
```

now we can open the file using `gimp`:

```bash
gimp 800.data
```

we can see that the file is a huge image. so we can change the offset, width and height to be able to see the flag.

we can use the settings from [DarkKnight](https://omarelshopky.github.io/ctf-writeups/cybertalents/Digital_Forensic/Monaliza/)'s writeup. thanks to him.

> Offset = 65913 Width = 737 Height = 6446

after changing the settings, we can see the flag.

## Flag

> Flag{P@!nting_i5_4wes0m3}

## References

- [https://en.wikipedia.org/wiki/Memory_forensics](https://en.wikipedia.org/wiki/Memory_forensics)

- [https://www.volatilityfoundation.org/](https://www.volatilityfoundation.org/)
