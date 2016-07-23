+++
date = "2016-07-11T17:00:25+08:00"
draft = true
title = "python libphonenumber"

+++

## What is libphonenumber?
libphonenumber is google's common Java, C++ and JavaScript library for parsing, formatting, and validating international phone numbers.
<!--more-->
## python libphonenumber
[python-libphonenumer](https://github.com/daviddrysdale/python-phonenumbers) is a Python port of Google's libphonenumber.

## Usage
* Parse a phone number
<pre>
<code class="python" style="font-size:10px;">
import phonenumbers
x = phonenumbers.parse('+8615801290852', None)
</code>
</pre>
* Get country code name from a parsed number object
<pre>
<code class="python" style="font-size:10px;">
import phonenumbers
x = phonenumbers.parse('+8615801290852', None)
cname = phonenumbers.region_code_for_number(x).lower()
print cname
</code>
<pre>
