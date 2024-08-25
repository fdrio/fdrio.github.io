---
layout: post
title:  "Analysis of The Tower Hanoi"
date:   2024-08-24 22:13:38 -0400
categories: jekyll update
mathjax: True
---
# Introduction:
The Tower of Hanoi puzzle was invented by the French mathematician Édouard Lucas in 1883. The setup consists of three equal rods, where a person can stacks disks of decreasing size.
The goal is to then move the disks in rod A to rod B with the following rules:

1. Only a single disk can be moved at a time. 
2. Only a disk from the top of a stack can be moved and must be placed on top of another stack or an empty rod
3. Only a disk smaller than itself can be placed on top of another disk.


# Analysis:

First let's define some notation. 
Let $H_n$ denote the minimum number of moves need to move the stack from rod A to rod B (wlog).



$$\sqrt{3x+1}$$ 



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
