# Challenge 33: flag shop

## Description

There's a flag shop selling stuff, can you buy a flag? [Source](https://jupiter.challenges.picoctf.org/static/64e724ad327f83ad833d9c6baa072b1f/store.c). Connect with `nc jupiter.challenges.picoctf.org 4906`.

### Tags

`picoCTF 2019` `General Skills`

### Points

`300`

## Solution

Before we connect to the server, we can take a look at the source code. we can see that the server will as us to input a number. (1/2/3)

1. to check th balance
2. to by a flag
3. to exit.

if we input 2, the server will to choose a flag. (1/2)

1. Defintely not the flag Flag
2. 1337 Flag

if we choose 2, it will say `337 flags cost 100000 dollars, and we only have 1 in stock Enter 1 to buy one` and if we choose 1, it will say `Not enough funds for transaction`.

if we choose 1, it will say `These knockoff Flags cost 900 each, enter desired quantity` and if we choose 1, it will say `The final cost is: 900 Your current balance after transaction: 200`.

Nothing interesting till now, but if we choose 2, it will say `These knockoff Flags cost 900 each, enter desired quantity` and if we choose 100000, it will say `The final cost is: 90000000 Your current balance after transaction: -89999000`.

what? the cost is negative? we can buy the flag for free? let's try it.

```bash
$ nc jupiter.challenges.picoctf.org 4906

Welcome to the flag store!
1. Check balance
2. Buy a flag
3. Exit
2
1. Definitely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one
1
YOUR FLAG IS: picoCTF{m0n3y_bag5_9c5fac9b}

```

But why? we can see that the cost is negative, although entered `90000000` multiplied by `900` is `81000000000` which is bigger than `2147483647` which is the max value of `int` in C. So because of the overflow, the cost became negative. and we minus the cost from our balance, and misusing a negative number is adding a positive number. so that is why we can buy the flag Now.

## Flag

> picoCTF{m0n3y_bag5_9c5fac9b}
