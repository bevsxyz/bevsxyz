---
title: What day is it again?
authors:
- admin
tags:
- algorithms
categories:
- code
date: "2021-03-02T08:00:00+05:30"
math: true
thebe: true
---

Recently I have been trying to up my game in programming and had started reading this [book](https://introcs.cs.princeton.edu/java/home/).  I came across an exercise that I thought was cool—so sharing it here.
The question is this, given three inputs - d (day)m, (month), and y (year), find the day of the week it falls on. And they go on to give a neat formula for the Gregorian calendar.

$$
y_0 = y - (14 - m) / 12
$$
$$
x = y_0 + y_0 / 4 - y_0 / 100 + y_0 / 400
$$
$$
m_0 = m + 12 * ((14 - m)/ 12) - 2
$$
$$
d_0 = (d + x + (31 * m_0)/12) \mod 7
$$

Well, it is pretty easy to do the calculations when you have the formula. But for me, the catch was that the formula gives an integer $\in [0-6]$ as output. My first reaction was to use conditionals. But that's naive, and this particular section bars me from using conditionals. And it dawned on me, it is merely straightforward to use a string array of weeks and use the output given by the formula as the index for it.

So here goes my simple python implementation:

{{% callout note %}}
After you click run it may take a minute to get started!
{{% /callout %}}

<pre data-executable>
def dayOfWeek(d, m, y):
    y_0 = y - (14 - m) // 12
    x = y_0 + y_0 // 4 - y_0 // 100 + y_0 // 400
    m_0 = m + 12 * ((14 - m)// 12) - 2
    d_0 = (d + x + (31 * m_0)//12) % 7
    days = ("Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday")
    print(days[d_0])
dayOfWeek(1,3,2021)
</pre>
