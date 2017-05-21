---
layout: post
title: JAVASCRIPT - How reviver function works with JSON.parse()
status: published
type: post
published: true
comments: true
category: blogs
tags: [js, json, JSON, parse, reviver, js function, mold json, modify json]
date: 2017-05-16T18:17:25+05:30
share: true
excerpt: In this blog post we are going to learn how JSON.parse works with a reviver function.
---

Sometimes we need to modify the JSON String received from the server side. The best way of doing it to use "reviver" function with JSON.parse.

This blog will guide you how to modify JSON String with JSON.parse function. 

The JSON.parse function parses a string to a JSON also it provides an optional second argument a "reviver" function that can be used to mold or modify the values being parsed. In JavaScript terms, the reviver function is a callback which will be invoked in turn on each of the property values in the JSON data being parsed. It has two arguments: key and value. You can delete a key-value pair from JSON by returning undefined, or the value can be modified based on your need, or the value can be returned unchanged.

Let's take a simple example to remove a key-value pair and modify the value of a key from JSON.


{% gist dhanendra-kumar/aa7d79b1b855d2f39435d1405e51f80a JsonReviverDeleteValue.js %}


Hope this helps