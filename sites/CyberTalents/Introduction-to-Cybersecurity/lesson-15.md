# Lesson 15: SQL Injection

> Lesson link:\
> *[https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/sql-injection](https://cybertalents.com/learn/introduction-to-cybersecurity/lessons/sql-injection)*

## Introduction

In this lesson, we will learn about SQL Injection, and how can we use it to retrieve data from the database.

> ### What is SQL Injection?
>
> #### SQL injection is a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its database. SQL injection attacks are possible when an application builds SQL queries using string concatenation or string formatting, but fails to sufficiently sanitize user-supplied input data. In this attack, the attacker-supplied SQL statements are usually executed with the privileges of the database account that the application is using. SQL injection attacks are possible mainly due to insufficient input validation

## Challenge

> Name:\
> *Easy access*

---

> Description:\
> *Only superpower makes you see unlimited view.*

## Solution

In this challenge, we have a website, and to login to get th flag.

lets try to send this payload in the username field with any password:

```sql
admin' or '1'='1; #
```

And That's it, we got the flag.

## Flag

> flag{!njection_3v3ry_wh3r3}

## References

- [https://www.w3schools.com/sql/sql_injection.asp](https://www.w3schools.com/sql/sql_injection.asp)

- [https://portswigger.net/web-security/sql-injection](https://portswigger.net/web-security/sql-injection)

- [https://www.acunetix.com/websitesecurity/sql-injection/](https://www.acunetix.com/websitesecurity/sql-injection/)

- [https://www.owasp.org/index.php/SQL_Injection](https://www.owasp.org/index.php/SQL_Injection)

- [https://www.netsparker.com/blog/web-security/sql-injection-cheat-sheet/](https://www.netsparker.com/blog/web-security/sql-injection-cheat-sheet/)
