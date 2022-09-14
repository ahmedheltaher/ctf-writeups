# Lesson 10: Directory Traversal

> Lesson Link:\
> *[https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/10-directory-traversal](https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/10-directory-traversal)*

## Introduction

In this lesson, we will learn about Directory Traversal, how to exploit it, How dangerous it is.

## Challenge

> Name:\
> *bean.*

---

> Description:\
> *Come back home Mr. Bean.*

## Solution

In this challenge, we have a website, and we need to find a way to get the flag.

Now, we need to do some research about `Directory Traversal`, and we will find that `Directory Traversal` is a vulnerability that allows an attacker to read files outside the web root directory.

Now, we can try to read the `flag.txt` file, by using `../` to go back to the parent directory.

all we got is `404 Not Found`.

so we need to find new ways to read the `flag.txt` file.

If do some research about `Directory Traversal`, we will find some tools that can help us to find all the paths in the website. by bruteforcing.

one of these tools is `dirsearch`. you can find it [here](https://github.com/maurosoria/dirsearch). follow the instructions in the `README.md` file to install it.

After running `dirsearch`, we will find that there is a directory called `files`.

if we hit the `files` directory, we will find lots of files, but no `flag.txt` file.

we could try `fils../` to go back to the parent directory, but we will a punch of different directories.

one of these directories is `home`, and if we hit the `home` directory, we will find a `flag.txt` file.

if we open the `flag.txt` file, we will find the flag.

## Flag

> FLAG{Nginx_nOt_aLWays_sEcUre_bY_The_waY}

## References

- [https://www.owasp.org/index.php/Testing_for_Local_File_Inclusion](https://www.owasp.org/index.php/Testing_for_Local_File_Inclusion)

- [https://www.oreilly.com/library/view/web-penetration-testing/9781788623377/1e4591d3-c427-4be1-a848-54d502a8f5d7.xhtml](https://www.oreilly.com/library/view/web-penetration-testing/9781788623377/1e4591d3-c427-4be1-a848-54d502a8f5d7.xhtml)
