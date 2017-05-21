---
layout: post
title: JAVASCRIPT - How string can be converted to a function using reviver.
status: published
type: post
published: true
comments: true
category: blogs
tags: [js, json, JSON, parse, reviver, js function, mold json, modify json]
date: 2017-05-17T18:17:25+05:30
share: true
excerpt: In this blog post we are going to learn how JSON.parse works with a reviver function.
---

Sometimes we have the issue to pass a JavaScript function in a JSON response from the server and use it on the client side.

This blog will guide you how to pass a javascript function in a JSON response from the server and how you can use it at the client side. 

Firstly, you have to know about the "reviver" function and also JSON.parse function working. As described in our previous <a href="../16/JSON-reviver-modify-json">blog</a>

Let's come to the main problem i.e. passing JavaScript function in JSON from the server side.

You have to create a json string at server side and put your json function in a string like -


{% gist dhanendra-kumar/1ae55792b6afaf7d542c1b064ab2d331 JsonReviverFunction.js %}


Hope this helps