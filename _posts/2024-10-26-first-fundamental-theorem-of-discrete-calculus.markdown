---
layout: post
title: "Fundamental Theorem of Discrete Calculus"
date: 2024-10-26 10:00:00 +0000
categories: [category1, category2]
tags: [tag1, tag2]
---
{%- include mathjax.html -%}
![Tower of Hanoi](/assets/images/first-fundamental-theorem-of-calculus/AxRsePkxHAsdxpzUBsfHU4-1200-80.jpg.webp)
An important question in mathematics are summations of polynomials. For example what is the closed formula for

$$ 
\begin{align*}
\sum_{x=0}^{n} x = ?
\end{align*}
$$

It turns out there is closed formula:

$$ 
\begin{align*}
\sum_{x=0}^{n} x = \frac{n(n+1)}{2}
\end{align*}
$$

This is a common and easy to prove formula but what about the summation of a monomial with a higher degree?
For example what is 

$$ 
\begin{align*}
\sum_{x=0}^{n} x^2 = ? 
\end{align*}
$$

While this one is also common and has a closed formula. We would like to have a systematic method of determining closed formulas summation of functions.
In classical calculus, we have the fundamental theorem(s) of calculus that help us find the summation of a function over infinitely many small parts.
The theorem states that if $f$ is uniformly continuous over the interval $[a,b] ⊂ ℝ$ then:

$$ 
\begin{align*}
∫_{a}^{b} f(x)dx = F(b) - F(a)  \\
\end{align*}
$$
where $F(x)$ is the antiderivative of $f(x)$.


On the other hand the first part of theorem states that given a function $F(x)$ defined on an interval $[a,b] ⊂ ℝ$.
Then for any $x ∈ [a,b]$:

$$ 
\begin{align*}
F(x) = ∫_{a}^{x} f(t)dt\\
\end{align*}
$$

we have 

$$ 
\begin{align*}
\frac{dF(x)}{dx} = f(x),  ∀x∈(a,b) \\
\end{align*}
$$

One can think of the fundamental theorem of calculus as two sides of the same coin that relate the derivate and antiderivate of a function. The question is then is there a similar relation in the discrete world. Recall that we cannot use the fundamental theorem of calculus here because our initial assumption of having function being uniformly continuous is never met. Discrete Calculus may provide an answer 


Recall from our initial question of what is the sum of $x^2$ from $0 … n$. It turns out that


$$ 
\begin{align*}
\sum_{x=0}^{n} x^2 = \frac{n(n+1)(2n+1)}{6} = \frac{2n^3 + 3n^2 + n}{6} 
\end{align*}
$$

If this were an integral, on $x^2$ then


$$ 
\begin{align*}
∫_{0}^{n}x^2dt = \frac{n^3}{3}\\
\end{align*}
$$


These two are clearly different but the resulting polynomial have the same degree. This is not a coincidence.













































To get started with the basics of discrete calculus, we define functions on sets of the form 

$ℕ_a := \\{ a, a+1, a+2, ... \\} $
where $a ∈ ℝ$. 

We can also define an upper bound of the set defined in the form of 
$ℕ_a^b := \\{ a, a+1, a+2, ...,b \\}$

where $a,b ∈ ℝ$ and $b - a ∈ ℤ^+$ 


**Forward difference operator**

Assume $f: ℕ_a^b → ℝ$, then we define the forward difference operator as 

$Δf(t) \:= f(t+1) - f(t)$, $∀ t ∈ ℕ_a^{b-1} $


**Forward jump operator**

Assume $σ: ℕ_a^{b-1} → ℝ$, then we define the forward jump operator as 

$σ(t) \:= t + 1 $


with this new operator $Δf(t)$ is equivalent as 


$Δf(t) \:= f(σ(t)) - f(t)$, $∀ t ∈ ℕ_a^{b-1} $


With these new operators we would like to find $Δ$ from our previous discussion. 
Given $ΔF(t) = F(t+1) - F(t)$, we can write $F(t+1) = F(t) + ΔF(t)$. 


Now for a given power of degree $n$. We get $Δ(t+α)^n = (t+α+1)^n - (t+α)^n$


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
