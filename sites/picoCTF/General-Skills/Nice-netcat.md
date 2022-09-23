# Challenge 4: Nice netcat

## Description

There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 21135`, but it doesn't speak English...

### Tags

`picoCTF 2021` `General Skills`

### Points

`15`

## Solution

We need to connect to the server using netcat. We can do this by running the following command:

```bash
$ nc mercury.picoctf.net 21135
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
97 
102 
100 
53 
102 
100 
97 
52 
125 
10
```

as we can see, the server sends us a bunch of numbers. we can redirect the output of the command to a file using output redirection:

```bash
nc mercury.picoctf.net 21135 > output.txt
```

now we have the output of the command in the `output.txt` file. we can open the file and see the numbers. we can convert the numbers to ASCII characters this little python script:

```python
with open("output.txt", "r") as f:
 for line in f:
  for num in line.split():
   print(chr(int(num)), end="")
```

we can run the script by running `python3 script.py`. we get the following output:

```bash
picoCTF{g00d_k1tty!_n1c3_k1tty!_afd5fda4}
```

as we can see, the script converts the numbers to ASCII characters and prints them. and we get the flag.

## Flag

> picoCTF{g00d_k1tty!_n1c3_k1tty!_afd5fda4}
