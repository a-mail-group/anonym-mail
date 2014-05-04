---
layout: default
title: Information Query Protocol
---

# {{ page.title }}

## 1. Overview

The IQP is a Protocol to be used to Fetch informations such as mailbox names, 

<br/>

## 2. The Protocol itself

Every Line is Terminated using CR-LF

<br/>

### 2.1 The ADDRINFO Command

The Client sends the Adress and gets an mailbox name and the public key associated with that address.

The adress can be eigther full qualified or relative.
Qualified: <code>john.doe#mail.undead.de</code>
Relative: <code>john.doe#</code>

<code>C: ADDRINFO john.doe#</code>

The server will respond with:

<code>S: OK</code>

<code>S: MAILBOX mb3772bbs</code>

<code>S: KEY 0sDkNDz0u5N3+EqJGCvjBuhAXFoGQzVIU4C2U2CZIGQ=</code>

or with:

<code>S: FAILED</code>

<br/>

### 2.2 The GET-INBOX-KEY Command

This command querys public keys to be used for the PUSH-Protocol-blob encryption

This command knows 2 variants:

1.: the local version querys the public key of the current server

<code>C: GET-INBOX-KEY</code>

<code>C: LOCAL</code>

2.: the FOR version querys the public key of the current server

<code>C: GET-INBOX-KEY</code>

<code>C: REMOTE mail.undead.de</code>

The server will respond with:

<code>S: OK</code>

<code>S: EXP 2014/02/01_01:00:00</code>

<code>S: +GXk5gCEzILSCYhY3nooIXvSDNu1vJGMg+YsT3aCu48=</code>

or with:

<code>S: FAILED</code>

<br/>

