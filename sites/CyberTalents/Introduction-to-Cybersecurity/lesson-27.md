# Lesson 27: Caesar Cipher

> Lesson Link:\
> *[https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/27-caesar-cipher](https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/27-caesar-cipher)*

## Introduction

Caesar cipher is one of the simplest and most widely known encryption techniques. It is a type of substitution cipher in which each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet. For example, with a shift of 3, A would be replaced by D, B would become E, and so on. The method is named after Julius Caesar, who used it in his private correspondence.

## Challenge

> Name:\
> *Hide Data*

---

> Description:\
> *I used to hide my data with a classic cypher, can you get the flag hidden inside? gur synt vf 2w68lsudym Vg vf cerggl rnfl gb frr gur synt ohg pna lbh frr vg v gbbx arneyl 1 zvahgr gb rapbqr guvf jvgu EBG13 tbbq yhpx va fbyivat gung*

## Solution

In this challenge, we are given a text, and we need to decode it to get the flag.

The text is encoded using a Caesar cipher, I Wrote a python script to decode the text.

```python
import string

letters = string.ascii_lowercase # "abcdefghijklmnopqrstuvwxyz"
print("Welcome to Caesar Cipher Decryption.\n")
encrypted = input("Enter the message you would like to decrypt: ").strip()

def decrypt(key):
    decrypted = ""

    for c in encrypted:

        if c in letters:
            position = letters.find(c)
            decrypted += letters[(position - key) % 26]
        else:
            decrypted += c

    return decrypted


for i in range(26):
    print("Trying: ", i)
    print(decrypt(i))
```

After running the script, we will be prompted to enter the text, and the script will try to decrypt the text using all possible keys, and we will get the following output:

```text
Welcome to Caesar Cipher Decryption.

Enter the message you would like to decrypt: gur synt vf 2w68lsudym Vg vf cerggl rnfl gb frr gur synt ohg pna lbh frr vg v gbbx arneyl 1 zvahgr gb rapbqr guvf jvgu EBG13 tbbq yhpx va fbyivat gung

...
Trying:  13
the flag is 2j68yfhqlz Vt is pretty easy to see the flag but can you see it i took nearly 1 minute to encode this with EBG13 good luck in solving that
...

```

We can see that the text is decoded using ROT13, and we can construct the flag from the text.

## Flag

> 2j68yfhqlz

after i wrote the script, i found out that there is a website that can decode the text for us, [this](https://www.dcode.fr/caesar-cipher) website can decode the text using all possible keys, and we can get the flag from the output.

## References

- [https://en.wikipedia.org/wiki/Caesar_cipher](https://en.wikipedia.org/wiki/Caesar_cipher)

- [https://www.dcode.fr/caesar-cipher](https://www.dcode.fr/caesar-cipher)
