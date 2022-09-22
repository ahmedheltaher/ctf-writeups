# Lesson 24: Intel-x86 Architecture Cover

> Lesson Link:\
> *[https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/24-intel-x86-architecture-cover](https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/24-intel-x86-architecture-cover)*

## Introduction

In this lesson we will cover the basics of the Intel-x86 architecture. We will start by learning about the registers and how to use them. Then we will learn about the memory and how to access it. Finally, we will learn about the instructions and how to use them.

## Challenge

> Name:\
> *bronze ASM*

---

> Description:\
> *his Challenge will help you understand how to analyze simple assembly code.*\
> *the flag is the parameter of the function int he following format ("FLAG{0_%X_0}" % parmter)*

## Solution

In this challenge, we are given a .asm file. after reading the file, we will find the following code:

```asm
fx:
        push    rbp
        mov     rbp, rsp
        mov     DWORD PTR [rbp-4], edi
        mov     eax, DWORD PTR [rbp-4]
        sal     eax, 3
        cmp     eax, 5744
        sete    al
        movzx   eax, al
        pop     rbp
        ret
```

So the function `fx` takes one parameter and, multiplies it by 8 (sal = shift arithmetic left, and 8 = 2^3), then compares it to 5744, if the result is equal to 5744, it returns 1, otherwise it returns 0.

So we need to find the parameter that makes the function return 1. So we need to solve the following equation:

`8 * parameter = 5744`

So the parameter is 718.

If we try to run the function with the parameter 718, like `FLAG{0_718_0}`, the flag will be incorrect.

Because the flag is in hex format, so we need to convert the parameter to hex, like `FLAG{0_2CE_0}`.

## Flag

> FLAG{0_2CE_0}

## References

- [Intel x86 Instruction Set Reference](https://www.felixcloutier.com/x86/)
