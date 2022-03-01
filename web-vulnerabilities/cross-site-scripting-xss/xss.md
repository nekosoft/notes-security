# Web Vulnerabilities: Cross-Site Scripting (XSS)

### Table of Contents

- [Overview](#overview)
- [What is XSS?](#what-is-xss)
- [Types of XSS](#types-of-xss)
  - [Reflected](#reflected)
  - [Stored or Persistent](#stored-or-persistent)
  - [DOM-based](#dom-based)

# Overview
Cross-Site Scripting (XSS) attack is when malicious scripts can be injected into a website. XSS can happen at any point you allow untrusted data to flow through your application. Without proper handling (such as encoding, validation and sanitization), the data may get interpreted or parsed and executed to an unsuspecting user. The goal of XSS is generally retrieving sensitive information from an unsuspecting user.

Injection occurs when:

1. Data enters a web application, which is sent to an interpreter and parsed
2. Data is sent back to the web user, without being validated for malicious content

The above can also be described as Sources and Sinks, where:
**Source** (data comes in from here) -> **Sink** (where the data ends)


# What is XSS?

- malicious scripts can be injected into websites via a http request
- malicious code is sent to or executed in the victim's browser
- web application believes the injection came from a trusted source
- depending on how the application interpets and parses the data, this puts a user at risk


# Sensitive Information
- cookies
- session tokens
- redirect the user to attacker controlled web content
- perform malicious operations on user's machine


# Types of XSS

## Reflected
- data received by a HTTP request
- includes arbitrary (usually malicious) JS
- usually in the form of some malicious javascript
- the script isn't stored anywhere (non-persistent)
- the response is reflected or echoed directly back to the user (intended victim)
- usually looks like a specially crafted url, phishing
- do not click links!

## Stored or Persistent
- injection is permanently stored, such as on a target web server
- can include databases, message forums, logs, comment fields
- user requests this information, which is actually a malicious script
- executes on victim's browser / machine

## DOM-Based
- DOM = Document Object Model, an interface that represents HTML/XML as a hierarchical tree structure (nodes like div's)
- the data flow never leaves the browser
- JS can programmatically interact with the DOM
- can be reflected or stored
- happens when browser parses page's content and inserted JS is executed (not parsed by a server, or even sent to a server, similar to reflected)


### Source and Sink for DOM Based vulns

Source:
- JS property accepting data that could be controlled by the attacker
- properties such as location.search, document.referrer string, document.cookie string

Sinks:
- potentially dangerous JS functions or DOM objects
- cause harm or unintended effects by the user, due to the malicious data injected
- sink because it parses the argument as JS
- example: document.body.innerHTML = allows attacker to inject malicious HTML and execute arbitrary JS
- example: eval()


# Common Causes


# ReactJS: Some preventions built-in
... but shouldn't be 100% trusted, especially when crafting your own methods.
- React JSX auto escape, read more here: [JSX Prevents Injections Attacks](https://reactjs.org/docs/introducing-jsx.html#jsx-prevents-injection-attacks)
- Dangerous function named for clarity and warning: [dangerouslySetInnerHTML - Read more from React Docs](https://reactjs.org/docs/dom-elements.html#dangerouslysetinnerhtml)

# Real Examples

# OWASP

# References
