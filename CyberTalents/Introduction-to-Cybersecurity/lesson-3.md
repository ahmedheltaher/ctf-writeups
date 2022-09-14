# Lesson 3: HTML

## Introduction

In this lesson, we will learn about HTML, some of the most common HTML tags, and how to use them. also, we will learn why HTML is important in Web Security.

## Challenge

> Name:\
> *htmlentities.*

---

> Description:\
> *True or False , htmlentities ( convert special characters to its html entity ) can't be exploited to run XSS payload ?*

## Solution

In this challenge, we just need to do some research about `htmlentities` and `XSS`, and we will find that `htmlentities` can be exploited to run XSS payload, so the answer is `False`.

## References

*HTML entities are characters that are not allowed in HTML. HTML entities are used to display reserved characters in HTML. HTML entities are also used to display special characters:*

```html
<!DOCTYPE html>
<html>
<body>

<h1>HTML Entities</h1>

<p>HTML entities are characters that are not allowed in HTML.</p>

<p>HTML entities are used to display reserved characters in HTML.</p>

<p>HTML entities are also used to display special characters like:</p>

<p>&lt;  => < </p>
<p>&gt;  => > </p>

</body>
</html>
```

if you are not familiar with HTML entities, you can read more about it [here](https://www.w3schools.com/html/html_entities.asp).
