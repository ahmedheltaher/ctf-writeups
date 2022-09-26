# Challenge 30: Based

## Description

To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29221`.

### Tags

`picoCTF 2019` `General Skills`

### Points

`200`

## Solution

When we connect to the server, we can see the server will send us this message:

```text
Let us see how data is stored
computer
Please give the 01100011 01101111 01101101 01110000 01110101 01110100 01100101 01110010 as a word.
...
you have 45 seconds.....

Input:

```

We need to convert the binary to text. we can use this little python script to do that:

```python
user_input = input("Enter Binary Stream: ")

user_input = user_input.split(" ")

converted_string = ""

for b in user_input:
    converted_string += chr(int(b, 2))

print(converted_string)
```

we can run the script and enter the binary stream and we will get ASCII text.

```bash
$ python3 binary_to_text.py
Enter Binary Stream: 01100011 01101111 01101101 01110000 01110101 01110100 01100101 01110010
computer
```

after we send the text to the server we will get another message:

```text
Please give me the  155 141 160 as a word.
Input:
```

we need to convert this octal to text. we can use this little python script to do that:

```python
user_input = input("Enter Octal Stream: ")

user_input = user_input.split(" ")

converted_string = ""

for b in user_input:
    converted_string += chr(int(b, 8))

print(converted_string)

```

we can run the script and enter the octal stream and we will get ASCII text.

```bash
$ python3 octal_to_text.py
Enter octal Stream: 155 141 160
map
```

after we send the text to the server we will get another message:

```text
Please give me the 7461626c65 as a word.
Input:
```

we need to convert this hexadecimal to text. we can use this little python script to do that:

```python
>>> bytes.fromhex('7461626c65').decode('utf-8')
'table'
```

after we send the text to the server we will get the flag:

```text
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_00a975ff}
```

Note: we can use this little python script to convert between different data encodings:

```python
import sys

def binary_to_text(binary):
    binary = binary.split(" ")

    converted_string = ""

    for b in binary:
        converted_string += chr(int(b, 2))

    return converted_string

def octal_to_text(octal):
    octal = octal.split(" ")

    converted_string = ""

    for b in octal:
        converted_string += chr(int(b, 8))

    return converted_string

def hex_to_text(hex):
    return bytes.fromhex(hex).decode('utf-8')

def text_to_binary(text):
    return ' '.join(format(ord(x), 'b') for x in text)

def text_to_octal(text):
    return ' '.join(format(ord(x), 'o') for x in text)

def text_to_hex(text):
    return ''.join(format(ord(x), 'x') for x in text)

def main():
    if len(sys.argv) != 3:
        print("Usage: python3 convert.py [binary|octal|hex|text] [value]")
        sys.exit(1)

    if sys.argv[1] == "binary":
        print(binary_to_text(sys.argv[2]))
    elif sys.argv[1] == "octal":
        print(octal_to_text(sys.argv[2]))
    elif sys.argv[1] == "hex":
        print(hex_to_text(sys.argv[2]))
    elif sys.argv[1] == "text":
        print("Binary: " + text_to_binary(sys.argv[2]))
        print("Octal: " + text_to_octal(sys.argv[2]))
        print("Hex: " + text_to_hex(sys.argv[2]))
    else:
        print("Usage: python3 convert.py [binary|octal|hex|text] [value]")
        sys.exit(1)

if __name__ == "__main__":
    main()
```

Note: the messages will be different every time you connect to the server.

## Flag

> picoCTF{learning_about_converting_values_00a975ff}
