---
layout: post
title: "Fundamental Theorem of Discrete Calculus"
date: 2024-10-26 10:00:00 +0000
categories: [category1, category2]
tags: [tag1, tag2]
---
{%- include mathjax.html -%}
![Tower of Hanoi](/assets/images/first-fundamental-theorem-of-calculus/AxRsePkxHAsdxpzUBsfHU4-1200-80.jpg.webp)
# Background:
The first fundamental theorem of calculus states the following:
Let $f(x)$ be a continuous function defined on $[a,b] ⊂ ℝ$. For a given function 

$$F(x) := ∫_a^x f(t) \,dt,  x ∈ [a,b]$$


Then $F$ is uniformly continuous and differentiable on $(a,b)$ such that 
$F'(x) = \frac{d}{dx} F(x) = f(x)$. 

Where $\frac{d}{dx}F$ is defined as $\frac{d}{dx}F = \lim_{h → ∞} \frac{F(x+h)-F(x)}{h}$



By re-arranging the first the fundamental theorem we can compute $F(x+α)$ for a given function $F$ and an arbitrary step $α$ such that $a ≤ x+α ≤b$: 

$$ 
\begin{align*}
F(x+α) =  F(x) + ∫_x^{x+α} f(t) \,dt &=  
F(x) + ∫_x^{x+α} dF(t)  \\
= F(x) + (F(x+\alpha) - F(x)) 
\end{align*}
$$



In continuous calculus this equation relates a displacement $F(x+α)$ with the original function $F(x)$ and the integral of its derivate $\frac{d}{dx} F(x)$ over its displacement interval plus some arbitrary constant that is eventually cancelled called $Δ$.

This is fine for the continuous case because we can find a derivate of $F(x)$, but what about discrete case where all of the assumptions of continuity are broken?
We would like to find a relation between $F(x+α)$ and $F(x)$, such that given an unknown value $Δ$ we get $F(x) + Δ  = F(x+α)$ where $α \in ℕ⧵\\{0\\} $

One might think, the answer is to add the derivate (it's not). 
For example, suppose $F(x) = x^2$, then what is $F(x+1)$?
We can write $(x+1)^2 = x^2 + Δ$, where $Δ$ is what we need to add to $F(x)$ to get to $F(x+1)$.
Solving for $Δ$ we get:

$$
\begin{align*}
(x+1)^2 &= x^2 + 2x + 1 \\
        &= x^2 + Δ \\
Δ &= 2x + 1
\end{align*}
$$

but this is would be wrong.

Going one degree up we will see that $Δ ≠ \frac{d}{dx}F(x)$ 

$$
\begin{align*}
(x+1)^3 = x^3 + Δ \\
Δ = 3x^2 +3x + 1 ≠ \frac{d}{dx}x^3 = 3x^2 
\end{align*}
$$

We are missing a few other non-constant terms. However, Discrete Calculus may provide an answer.











# Analysis:
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
