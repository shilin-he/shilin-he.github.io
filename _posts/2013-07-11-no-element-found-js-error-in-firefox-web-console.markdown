---
layout: post
title:  "'no element found' JavaScript error in Firefox Web Console"
date:   2013-06-26 13:03:31
categories: javascript firefox webapi
---

Calling an ASP.Net WebAPI action which only returns HTTP status code will cause
a 'no element found' JavaScript error inside the Firefox Web Console. The reason 
is that Firefox is expecting some XML data returning from the server after an 
AJAX call. My solution is to return an object even for PUT and DELETE operations.

This [article][http://james.revillini.com/2006/10/27/%E2%80%98no-element-found%E2%80%99-in-firebug-or-firefox-javascript-console-part-2/] discusses the same problem.  


