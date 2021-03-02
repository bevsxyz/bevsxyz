---
title: What day is it again?
authors:
- admin
tags:
- algorithms
categories:
- code
date: "2021-03-04T08:00:00+05:30"
---

Recently I have been trying to up my game in programming and had started reading this book.  I came across an exercise that I thought was cool—so sharing it here.
The question is this, given three inputs - m (month), d (day), and y (year), find the day of the week it falls on. And they go on to give a neat formula for the Gregorian calendar.


Well, it is pretty easy to do the calculations when you have the formula. But for me, the catch was that the formula gives an integer in [0-6] as output. My first reaction was to use conditionals. But that's naive, and this particular section bars me from using conditionals. And it dawned on me, it is merely straightforward to use a string array of weeks and use the output given by the formula as the index for it.
