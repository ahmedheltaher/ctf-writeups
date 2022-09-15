# Lesson 11: Sensitive Data Exposure

> Lesson Link:\
> *[https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/11-sensitive-data-exposure](https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/11-sensitive-data-exposure)*

## Introduction

In this lesson, we will learn about Sensitive Data Exposure, how can we find some unintentionally exposed sensitive data.

## Challenge

> Name:\
> *Maximum Courage*

---

> Description:\
> *Max prefers to learn by practicing and not just reading all day, so he set up a webserver and hopes it stays secret, can you prove it has a weakness?*

## Solution

In this challenge, we have a website, and we need to find a way to get the flag.

If we take a look at the home page of the website, we will find a link to the `flag.php` file, so let's take a look at it.

```php
You can't view this flag directly.
<!-- PHP source doesn't appear on HTML comments -->
```

So, we can't view the flag directly, we need to find a way to view the full source code of the php file.

We Could try to use directory enumeration any other helpful paths.

aAfter some enumeration, we will find theses paths:

```bash
/flag.php
/.git
```

So, we have a php file, and a `.git` directory, let's take a look at the `.git` directory. we find that it is forbidden, so we need to find a way to bypass it.

There is a collection of git tools, and one of them is `gitdumper`, we can use it to dump the `.git` directory.

```bash
gitdumper http://wlemxwl32epheze6eg23gmgi834k4nzy52xmanzk-web.cybertalentslabs.com/.git/ ./maximumCourage
```

After dumping the `.git` directory, we still got nothing useful at the first look, but if we used another tool called `gitextractor`, like this:

```bash
gitextractor ./maximumCourage ./maximumCourageExtracted
```

we will get an a new directory called `maximumCourageExtracted`, and inside it, we will find a directory called `0-190de370286e98dda6813ac9c05f679ad60d9f9c`, and inside it, we will find a file called `flag.php`, and if we take a look at it, we will find the flag.

```php
You can't view this flag directly.
<!-- PHP source doesn't appear on HTML comments -->
<?php
exit();
die();
$secret_key = 'be607453caada6a05d00c0ea0057f733';
?>%
```

So, here we have the flag.

## Flag

> be607453caada6a05d00c0ea0057f733

## References

*Sensitive data exposure is a vulnerability that occurs when an application or service exposes sensitive data to an attacker. Sensitive data can include anything from personally identifiable information (PII) to financial information to intellectual property. Sensitive data exposure can occur in a variety of ways, including:*\
*• Exposing sensitive data in logs or error messages*\
*• Exposing sensitive data in URLs*\
*• Exposing sensitive data in HTML comments*\
*• Exposing sensitive data in HTML source code*\
*• Exposing sensitive data in JavaScript source code*\
*• etc...*

*Sensitive data exposure is a common vulnerability that can lead to a variety of attacks, including:*\
*• Account takeover*\
*• Data theft*\
*• Data manipulation*\
*• etc...*

- [https://github.com/internetwache/GitTools](https://github.com/internetwache/GitTools)
