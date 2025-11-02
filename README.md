# HTML Decode vs. HTML Encode: Complete Guide

Welcome to the **HTML Decode vs. HTML Encode** GitHub repository! This repository provides a comprehensive guide on understanding the differences between HTML encoding and decoding, how they work, and when to use each.

The contents here are based on the full article published on [Meniya.com](https://www.meniya.com/blog/html-decode-vs-html-encode-complete-guide).

## Table of Contents
- [Introduction](#introduction)
- [What is HTML Encoding?](#what-is-html-encoding)
- [What is HTML Decoding?](#what-is-html-decoding)
- [When to Use HTML Encoding vs. HTML Decoding](#when-to-use-html-encoding-vs-html-decoding)
- [Common Use Cases for HTML Encoding](#common-use-cases-for-html-encoding)
- [Common Use Cases for HTML Decoding](#common-use-cases-for-html-decoding)
- [HTML Encode and Decode Functions in JavaScript](#html-encode-and-decode-functions-in-javascript)
- [Best Practices](#best-practices)
- [References](#references)

## Introduction

In web development, HTML encoding and decoding are crucial for ensuring that content displayed on websites is rendered properly and securely. Whether you're dealing with user input or creating dynamic content, understanding the difference between encoding and decoding HTML entities is vital to ensure that content is processed and displayed correctly.

In this guide, we will explain both concepts in detail and show you when to use HTML encoding or decoding.

## What is HTML Encoding?

HTML encoding is the process of converting special characters (like `<`, `>`, `&`, `"` etc.) into their corresponding HTML entity codes. This helps prevent issues such as:

- Displaying HTML special characters properly
- Avoiding XSS (Cross-Site Scripting) attacks by neutralizing potentially malicious input

For example, the character `<` becomes `&lt;` in HTML encoding.

### Example:
```html
&lt;div&gt;This is a div&lt;/div&gt;
````

## What is HTML Decoding?

HTML decoding is the process of converting HTML entity codes back into their original characters. It’s used to convert encoded HTML entities back to the readable form that browsers can render properly.

For example, `&lt;` will be decoded back into `<` during HTML decoding.

### Example:

```html
<div>This is a div</div>
```

## When to Use HTML Encoding vs. HTML Decoding

* **HTML Encoding**: Use encoding when displaying dynamic or user-generated content to the web page, such as text in forms, comments, or inputs, to ensure special characters do not interfere with the HTML structure or trigger vulnerabilities.
* **HTML Decoding**: Use decoding when processing the content after it’s encoded, such as when rendering or displaying HTML content that is safely decoded for browser rendering.

## Common Use Cases for HTML Encoding

* Displaying user input (comments, forms, etc.) in a safe manner.
* Preventing XSS (Cross-Site Scripting) attacks by encoding potentially dangerous characters.
* Encoding text to display code snippets or special symbols.

### Example:

If a user submits a script tag in a form:

```html
<script>alert('Hacked!');</script>
```

It can be encoded as:

```html
&lt;script&gt;alert(&#39;Hacked!&#39;);&lt;/script&gt;
```

## Common Use Cases for HTML Decoding

* Displaying previously encoded content in its readable form.
* Rendering dynamic HTML content that includes both encoded and decoded HTML entities.
* Processing data for output, where you want to display encoded entities as their character equivalents.

## HTML Encode and Decode Functions in JavaScript

In JavaScript, you can use built-in methods or create your own functions to encode and decode HTML entities.

### HTML Encoding Function (JavaScript):

```javascript
function htmlEncode(str) {
  var element = document.createElement('div');
  if (str) {
    element.innerText = str;
    element.textContent = str;
  }
  return element.innerHTML;
}
```

### HTML Decoding Function (JavaScript):

```javascript
function htmlDecode(str) {
  var element = document.createElement('div');
  if (str) {
    element.innerHTML = str;
  }
  return element.innerText || element.textContent;
}
```

## Best Practices

* **Encode user input**: Always encode user-generated content before displaying it on your website.
* **Use a secure encoding method**: When encoding content for storage or display, ensure you are using the appropriate methods to prevent malicious code from executing.
* **Use built-in browser functions**: Utilize built-in functions like `textContent` and `innerHTML` for encoding and decoding to reduce the risk of security vulnerabilities.

## References

* [HTML Entity Encoding](https://www.w3.org/TR/html5/syntax.html#character-references)
* [OWASP XSS Prevention Cheat Sheet](https://owasp.org/www-community/xss-prevention)
* [Meniya.com Blog - HTML Decode vs. HTML Encode: Complete Guide](https://www.meniya.com/blog/html-decode-vs-html-encode-complete-guide)

## Contribution

We welcome contributions to improve and extend this guide! If you find an error, have an idea for a new section, or want to add more examples, feel free to submit a pull request.

1. Fork this repository.
2. Create a new branch (`git checkout -b new-feature`).
3. Make your changes.
4. Push to your forked repository.
5. Open a pull request.

## License

This repository is licensed under the MIT License. See the LICENSE file for more information.

---

Thanks for checking out the **HTML Decode vs HTML Encode: Complete Guide**! We hope this guide helps you understand these important concepts in web development. If you have any questions or need further clarification, feel free to open an issue or submit a pull request.
