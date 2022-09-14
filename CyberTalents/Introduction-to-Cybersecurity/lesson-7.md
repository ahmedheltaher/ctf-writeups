# Lesson 7: Encoding

> Lesson Link:\
> *[https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/7-encoding](https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/7-encoding)*

## Introduction

In this lesson, we will learn about Encoding, some of the most common Encoding types, and how to use them. also, we will learn why Encoding is important in Web Security.

> ### Encoding
>
> #### Encoding is the process of converting data from one format to another. Encoding is used to protect data from being corrupted during transmission. Encoding is also used to protect data from being read by unauthorized users
>
> ### Decoding
>
> #### It is the reverse of the encoding process

## Challenge

> Name:\
> *who am i?*

---

> Description:\
> *Do not Start a fight you can not stop it*

## Solution

In this challenge, we Need to spin up the given website, we will be presented with a login page, so we will try to login with some random credentials, and we will get nothing.

if we take a look at the source code of the page, we will find the following comment:

```html
<!-- 
	Guest Account:
	-=-=-=-=-=-=-=-
	Username:Guest
	Password:Guest  
-->
```

so we will try to login with the given credentials, and we redirected to the following page:

```html
   Welcome, Guest !

   Access Denied. You have no admin priviliges, Please login with an administrator account
```

If we take a look at the cookies, we will find a cookie called `Authentication` that has a value of `bG9naW49R3Vlc3Q%3D`.

if we decode the value of the cookie using base64, we will get `login=Guest7`.

so we can try to change the value of the cookie to `login=admin`, encode it using base64, and see what happens.

if we change the value of the cookie to `login=admin`, encode it using base64, and refresh the page, we will get the following message:

```html
   Welcome, Administrator !

   Congratulation. Your Flag iS :
   FLag{B@D_4uTh1Nt1C4Ti0n}
```

## Flag

> FLag{B@D_4uTh1Nt1C4Ti0n}

## References

if you want to learn more about Encoding, you can check the following resources:

- [https://www.wikiwand.com/en/Character_encoding](https://www.wikiwand.com/en/Character_encoding)

- [https://www.wikiwand.com/en/Base64](https://www.wikiwand.com/en/Base64)
