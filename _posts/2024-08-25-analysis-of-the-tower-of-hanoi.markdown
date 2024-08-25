---
layout: post
title:  "Analysis of The Tower Hanoi"
date:   2024-08-25 16:06:38 -0400
categories: jekyll update
---
{%- include mathjax.html -%}
# Introduction:
The goal is to then move the disks in rod $A$ to rod $B$ with the following rules:

1. Only a single disk can be moved at a time. 
2. Only a disk from the top of a stack can be moved and must be placed on top of another stack or an empty rod
3. Only a disk smaller than itself can be placed on top of another disk.

![Tower of Hanoi](/assets/images/analysis-of-the-tower-hanoi-problem/300px-Tower_of_Hanoi.jpeg)

A much older instance of this problem can be found in the Tower of Brahma, which supposedly consisted of 64 disks. According to legend, Brahma placed the 64 disks on the first rod and instructed the priests to transfer the disks from one rod to the other using the rules mentioned in the beginning. Once they finished, the world would end. We will show that the number of moves the priests would have to do is exactly $18,446,744,073,709,551,615$ for the world to end. 
# Analysis:

First let's define some notation.

Let $T_n$ denote the minimum number of moves need to move the stack from rod $A$ to rod $B$ without loss of generality.

**Let's start with some examples**

$T_0 = 0$, since there is nothing to move. Anyone familiar with recursion might see why going through this step could be useful.

$T_1 = 1$, since there is only one disk to move. We can simply move the only disk from rod $A$ to $B$.

$T_2 = 3$, the top smallest disk can be moved to the auxiliary rod $C$, then the largest disk can be moved to $A$ and finally we move the smallest disk from $C$ to $B$.

Similarly,

$T_3 = 7$

$T_4 = 15$

$T_5 = 31$

$T_6=63$ and so on.


We can already see a few interesting patterns, at least initially. The number of moves seems to always be an odd number except for $T_0$.


**Generalization**

But what would be the optimal way to transfer $n$ disks? 

In order to begin the generalization, we can think of an initial generalized strategy. First we transfer the smallest $n-1$ disks to an auxiliary rod $C$, move the largest final disk to $B$ and then move the $n-1$ disks to $B$.

This gives us an inequality of the form 

$$T_n \leq 2T_{n-1} + 1$$

but can we do better? No, because at some point we have to move the largest disk after we moved the $T_{n-1}$ disk and then move $T_{n-1}$ back. Rules $1,2,3$ prevents us from doing any better. Therefore we can write 

$T_n \geq 2T_{n-1} + 1 $


With these two inequalities we can confidently write 

$T_n = 2T_{n-1} + 1$

Now to solve the recurrence equation.

$T_n = 2T_{n-1} +1$

$ = 2(2T_{n-2}+1) +1$

$ = 2^2T_{n-2}+2 +1$

$ = 2^3T_{n-3}+ 2^2+2 +1$

You may start to see the pattern that $T_n$ can be written as 

$$ T_n = 2^n T_0 + \sum_{k=0}^{n-1}2^k$$ 

and recall from our very first example that $T_0 = 0$. So our final equation simplifies to

$$ T_n = \sum_{k=0}^{n-1}2^k$$

This is a Geometric series of the form 

$$S_n = \sum_{k=0}^{n} r^k = \dfrac{1-r^{n+1}}{1-r}$$ 

with $r=2$.

Therefore $T_n = \dfrac{1-2^n}{1-2} = 2^n -1$.


Now we have found a closed formula for the minimum number of moves need for a Tower of Hanoi with an arbitrary value of $n$.
With this equation we can evaluate the number of moves need for the Tower of Brahma to be $2^{64}-1 = 18,446,744,073,709,551,615$




<!-- 
You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.MARKUP`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. After that, include the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/

-->
