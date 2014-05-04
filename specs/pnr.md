---
layout: default
title: Protocol number retrieval
---

# {{ page.title }}

## Background

As an inofficial "standard" A-Mail has no proper DNS-Integration like E-Mail. If, for example, someone sends a E-Mail to john.doe@undead.de, the mail system will look for the MX-record of undead.de on the DNS-Server. But for A-Mail, there won't be special MX-like, DNS-records. Thats why the Service Information Protocol (S.I.P.) was made. If a system send a A-Mail to john.doe#mail.undead.de, it will lookup the IP Adress for mail.undead.de, than it will send a S.I.P. query to this IP Adress on port 64000.

The S.I.P. is a protocol that maps strings to JSON objects.

<br/>

This document describes the names and the JSON structure, served by the S.I.P. daemon, required for correct A-Mail Service Information Retrieval.

<br/>

## Specs

### "amail.push"

this is a query for the PUSH server port

{% highlight javascript %}
{
 "port": 10203,
 "vsep_port": 10223,
 "vsep_key": "uKzr2uRVvUnP1GRN5iGrwImrm4TNQwI6gXbC2B2y2nA="
}
{% endhighlight %}

<br/>

* port: optional for non-encrypted PUSH-protocol
* vsep_port: optional for vsep-encrypted PUSH-protocol
* vsep_key: optional for vsep-key

<br/>

### "amail.iqp"

this is a query for the IQP server port

the result is similar to that of "amail.push"

