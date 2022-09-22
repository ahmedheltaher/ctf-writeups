# Lesson 28: Hash Cracking

> Lesson Link:\
> *[https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/28-hash-cracking](https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/28-hash-cracking)*

## Introduction

Hashing is a one-way function that takes a string of any length and returns a fixed-length string. Hashing is used to store passwords in a database. The password is hashed and stored in the database instead of the password itself. This way, if the database is compromised, the attacker will not be able to get the passwords. Hashing is also used to verify the integrity of files. The hash of a file is stored in a database and when the file is downloaded, the hash of the downloaded file is calculated and compared to the stored hash. If the hashes match, the file is not corrupted.

## Challenge

> Name:\
> *Guess The Password*

---

> Description:\
> *A hacker leaked the below hash online.Can you crack it to know the password of the CEO? the flag is the password Hash: 06f8aa28b9237866e3e289f18ade19e1736d809d*

## Solution

In this challenge, we are given a hash. and we need to crack it to get the password of the CEO. We can use [this](https://hashes.com/en/tools/hash_identifier) website to identify the hash type. After uploading the hash, we will get the following result:

```text
Hash: 06f8aa28b9237866e3e289f18ade19e1736d809d
Hash type: SHA-1
```

We can use [this](https://hashes.com/en/decrypt/hash) website to crack the hash. After uploading the hash, we will get the following result:

```text
06f8aa28b9237866e3e289f18ade19e1736d809d:jrahyn+
```

And we Got the password of the CEO.

## Flag

> jrahyn+

## References

- [https://en.wikipedia.org/wiki/Hash_function](https://en.wikipedia.org/wiki/Hash_function)

- [https://en.wikipedia.org/wiki/Password_hashing](https://en.wikipedia.org/wiki/Password_hashing)

- [https://en.wikipedia.org/wiki/File_verification](https://en.wikipedia.org/wiki/File_verification)

- [https://en.wikipedia.org/wiki/Secure_Hash_Algorithms](https://en.wikipedia.org/wiki/Secure_Hash_Algorithms)

- [https://en.wikipedia.org/wiki/MD5](https://en.wikipedia.org/wiki/MD5)

- [https://en.wikipedia.org/wiki/SHA-1](https://en.wikipedia.org/wiki/SHA-1)

- [https://en.wikipedia.org/wiki/SHA-2](https://en.wikipedia.org/wiki/SHA-2)

- [https://en.wikipedia.org/wiki/SHA-3](https://en.wikipedia.org/wiki/SHA-3)
