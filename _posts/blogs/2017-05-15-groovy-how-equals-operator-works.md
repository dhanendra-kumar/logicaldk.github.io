---
layout: post
title: GROOVY - How '==' equality works (Operator Overloading)
status: published
type: post
published: true
comments: true
category: blogs
tags: [GROOVY, GRAILS, ==, equals, equality, operator overloading, equal functionality]
date: 2017-05-15T20:17:25+05:30
share: true
excerpt: In this blog post we are going to learn how groovy's overloaded '==' operator works.
---

This blog will guide you how to use '==' operator to get appropriate output. Let's do it with examples, Suppose we have code as given below.


{% gist dhanendra-kumar/3fad90484920db987137a45bb550e877 EqualityGroovy.groovy  %}


This looks simple and you may guess correct output, once you execute the code you will get the correct output like below - 

{% gist dhanendra-kumar/15025f6203cadc10f512637a7e0bc5e0 EqualityGroovyOutput.groovy %}


If you notice that "==" & equals() return different output (we are expecting "true" at line no 7 & 8) but output returns false. Now, the real question why?

1. Is there any bug in groovy?
2. Is '==' called equals()?

There are many questions come to your mind but here is the reason why it is happening.

Actually the implementation of "==" in groovy slightly different from Java "==" implementation

Behavior of "=="

In Java, 
	
	"==" means equality of primitive types or identity for objects.

In Groovy,

    if they are Comparable, "==" translates to "a.compareTo(b)==0"
    if they are not Comparable, "==" translates to "a.equals(b)"
    	
    To check for identity, there is a method "is()". E.g. a.is(b)


Hope this helps