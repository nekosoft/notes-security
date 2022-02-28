# Web Vulnerabilities: XSS

### Table of Contents

- [Overview](#overview)
- [What is XSS?](#what-is-xss)
- [Types of XSS](#types-of-xss)

# Overview
An important part of developing web applications is data sanitization, otherwise you could leave a web application vulnerable.

# What is XSS?
- malicious scripts can be injected into websites
- malicious code is sent to or executed in the victim's browser
- web application believes the injection came from a trusted source
- depending on how the application interpets and parses the data, this puts a user at risk


# Sensitive Information
- cookies
- session tokens
- redirect the user to attacker controlled web content
- perform malicious operations on user's machine

# Injection

Injection occurs when:

Data enters a web application, which is sent to an interpreter and parsed
Data is sent back to the web user, without being validated for malicious content

Source (data comes in from here -> Sink (where the data ends)

# Types of XSS

## Reflected
- reflected off the web server
- usually in the form of some malicious javascript
- the script isn't stored anywhere
- reflected directly back to the user (intended victim)
- usually looks like a specially crafted url, can rely on phishing
- do not click links!

## Stored or Persistent
- injection is permanently stored, such as on a target web server
- can include databases, message forums, logs, comment fields
- user requests this information, which is actually a malicious script
- executes

## DOM-Based
- DOM = Document Object Model
- the data flow never leaves the browser
- JS can programmatically interact with the DOM
can be reflected or stored
happens when browser parses page's content and inserted JS is executed (not parsed by a server, or even sent to a server)
- Source and Sink for DOM Based vulns

Source:
- JS property accepting data that could be controlled by the attacker
- properties such as location.search, document.referrer string, document.cookie string

Sinks:
- potentially dangeours JS functions or DOM objects
- cause harm or unintended effects by the user, due to the malicious data injected
- sink because it parses the argument as JS
- example: document.body.innerHTML = allows attacker to inject malicious HTML and execute arbitrary JS
- example: eval()


# Common Causes

# Real Examples

# OWASP

# References
