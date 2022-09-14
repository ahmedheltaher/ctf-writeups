# Lesson 6: Hashing

> Lesson Link:\
> *[https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/6-hashing](https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/6-hashing)*

## Introduction

Hashing is a one-way function that takes a string of any length and returns a fixed-length string. The output of the function is called a hash. Hashing is used to verify the integrity of data. It is also used to store passwords in a database. The hash of a password is stored in the database instead of the password itself. This way, if the database is compromised, the attacker will have a hard time getting the passwords.

> ### Hashing Algorithms
>
> #### There are many hashing algorithms. The most common ones are MD5, SHA1, SHA256, SHA512, and bcrypt. The most secure ones are bcrypt and SHA512. The most common ones are MD5 and SHA1. MD5 and SHA1 are insecure because they are fast to compute and have a small output. This means that it is easy to find two different inputs that have the same output. This is called a collision. A collision is a weakness in a hashing algorithm. A collision means that two different inputs have the same output. This means that the output of the function is not unique. This means that the function is not a one-way function. This means that the function is not secure

## Challenge

> Name:\
> Hash3rror.

----

> Description:\
> *we got this corrupted hash password from a Pcap file with a note (password = sha-1(hash-result))*.
*HASH:77be5d24ed2e3e590045e1d67e8450d2799c19f48ede46804a8734e287df120f*

## Solution

In This challenge, we need to find the original password. We have a corrupted hash password and a note that says that the password is the sha-1 of the hash result. So, we need to find the sha-1 of the hash result.

So We First need to find the hash result. but first, we need to know the hashing algorithm. We can use [this website](https://hashes.com/en/tools/hash_identifier) to identify the hashing algorithm.

if we paste the hash in the website, we will get a message that tells us that the hashing algorithm is `SHA-256`.

Now we need to decrypt the hash. We can use [this website](https://md5decrypt.net/en/Sha256/) to decrypt the hash.

if we paste the hash in the website, we will get a message that tells us that the hash result is `s3cr3tpassword`.

Now we need to find the sha-1 of the hash result. We can use [this website](https://md5decrypt.net/en/Sha1/) to find the sha-1 of the hash result.

if we paste the hash result in the website, we will get a message that tells us that the sha-1 of the hash result is `83874343435092cb681c0d558a84bfeb389c32ed`.

## Flag

> 83874343435092cb681c0d558a84bfeb389c32ed

## References

if you are not familiar with hashing, you can read more about it [here](https://en.wikipedia.org/wiki/Hash_function).

if you are not familiar with sha-1, you can read more about it [here](https://en.wikipedia.org/wiki/SHA-1).

if you are not familiar with sha-256, you can read more about it [here](https://en.wikipedia.org/wiki/SHA-2).
