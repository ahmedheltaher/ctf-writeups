# Challenge 27: Serpentine

## Description

Find the flag in the Python script!\
[Download Python script](https://artifacts.picoctf.net/c/94/serpentine.py)

### Tags

`Beginner picoMini 2022` `General Skills` `python`

### Points

`100`

## Solution

If we run this script. it will ask us to enter a choice from (a/b/c/). if we enter `a` it will print

```text
-----------------------------------------------------
Look how far you've come!
-----------------------------------------------------
```

if we enter `b` it will print

```text
Oops! I must have misplaced the print_flag function! Check my source code!
```

if we enter `c` it will close the program.

We Need to make the program print the flag.

if we look at the source code we will see this:

```python
....
    if choice == 'a':
      print_encouragement()
      
    elif choice == 'b':
      #print('\nOops! I must have misplaced the print_flag function! Check my source code!\n\n')
      print_flag()
    elif choice == 'c':
      sys.exit(0)
      
    else:
      print('\nI did not understand "' + choice + '", input only "a", "b" or "c"\n\n')

....
```

as we can see, if we enter `b` it will print the message `Oops! I must have misplaced the print_flag function! Check my source code!`.

We Just Need to call the function `print_flag()`.

If we run the code with `python3 serpentine.py` and enter `b` we will get the flag.

```bash
$ python3 serpentine.py


    Y
  .-^-.
 /     \      .- ~ ~ -.
()     ()    /   _ _   `.                     _ _ _
 \_   _/    /  /     \   \                . ~  _ _  ~ .
   | |     /  /       \   \             .' .~       ~-. `.
   | |    /  /         )   )           /  /             `.`.
   \ \_ _/  /         /   /           /  /                `'
    \_ _ _.'         /   /           (  (
                    /   /             \  \
                   /   /               \  \
                  /   /                 )  )
                 (   (                 /  /
                  `.  `.             .'  /
                    `.   ~ - - - - ~   .'
                       ~ . _ _ _ _ . ~

Welcome to the serpentine encourager!


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) b

picoCTF{7h3_r04d_l355_7r4v3l3d_aa2340b2}
```

## Flag

> picoCTF{7h3_r04d_l355_7r4v3l3d_aa2340b2}
