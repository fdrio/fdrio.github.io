---
layout: post
title: "Fundamental Theorem of Discrete Calculus"
date: 2024-10-26 10:00:00 +0000
categories: [category1, category2]
tags: [tag1, tag2]
---
{%- include mathjax.html -%}
![Clock](/assets/images/first-fundamental-theorem-of-calculus/AxRsePkxHAsdxpzUBsfHU4-1200-80.jpg.webp)

# Background
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

While this one is also common and has a closed formula. 
We would like to have a systematic method of determining closed formulas for the summation of functions.
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

One can think of the fundamental theorem of calculus as two sides of the same coin that relate the derivate and antiderivate of a function. 
The question is then is there a similar relation in the discrete world. 
Recall that we cannot use the fundamental theorem of calculus here because our initial assumption of having a function being uniformly continuous is never met.  

Recall from our initial question of what is the sum of $x^2$ from $0 … n$. It turns out that


$$ 
\begin{align*}
\sum_{x=0}^{n} x^2 = \frac{n(n+1)(2n+1)}{6} = \frac{2n^3 + 3n^2 + n}{6} 
\end{align*}
$$

If this were an integral, on $x^2$ then


$$ 
\begin{align*}
∫_{0}^{n}x^2dx = \frac{n^3}{3}\\
\end{align*}
$$


These two are clearly different but the resulting polynomial have the same degree. This is not a coincidence.
Similarly, for derivates we know


$$ 
\begin{align*}
\frac{dx^2}{dx} = 2x
\end{align*}
$$

which means that at every point $x$ the gradient of the tangent at each point is $2x$. 
But what about the rate of change of the discrete case? 
This is where Discrete Calculus may provide an answer.

### Definitions
To get started with the basics of discrete calculus, we must first define functions on sets of the form 

$ℕ_a := \\{ a, a+1, a+2, ... \\} $
where $a ∈ ℝ$. 

We can also define an upper bound of the set defined in the form of $ℕ_a^b := \\{ a, a+1, a+2, ...,b \\}$ where $a,b ∈ ℝ$ and $b - a ∈ ℤ^+$. 

We would like to find a discrete version of the derivative of a function.
We know the most basic incremental change for the discrete case is $+1$. 
So our "discrete  derivative" is really 

$$ 
\begin{align*}
\frac{f(x+1) - f(x)}{x+1-x} = f(x+1) - f(x)
\end{align*}
$$


since $x+1 - x = 1$.

Let's denote $Δ$ to be this discrete rate of change called the forward difference operator.

**Forward difference operator**

Assume $f: ℕ_a^b → ℝ$, then we define the forward difference operator as 

$Δf(t) \:= f(t+1) - f(t)$, $∀ t ∈ ℕ_a^{b-1} $

With this new operator, we can now answer the question of what do we need to add to $f(x)$ to get $f(x+1)$. 
Rearraging the question, we get the answer as

$$ 
\begin{align*}
Δf(x) = f(x+1) - f(x)\\
f(x+1) = Δf(x) + f(x)
\end{align*}
$$

Now one thing to note is the summation of these deltas $ΣΔf$ gives you the original function $f$. Namely $ΣΔf = f$. The proof is rather similar to the fundamental theorem of calculus.



## Fundamental Theorem of Discrete Calculus:

##### **Theorem**:

$$ 
\begin{align*}
ΔF(x) = f(x) ⟷ \sum_{n \in ℕ_a^{b-1}}f(n) = F(b) - F(a)
\end{align*}
$$


##### **Proof**:

**- First part:**

Let $G(x)$ be the antidifference of $f(x)$ and let $F(x)$ be any antidifference of $f(x)$. Such that

$$ 
\begin{align*}
G(x) = \sum_{n=a}^{x-1} f(n) 
\end{align*}
$$

$$ 
\begin{align*}
F(x) = G(x) + C  
\end{align*}
$$

Applying the forward difference operator on $F$ we get 

$$ 
\begin{align*}
\Delta_x F(x) = \Delta_x G(x) + \Delta_x C = G(x+1) - G(x) = \sum_{n=a}^{x}f(n) - \sum_{n=a}^{x-1}f(n) = f(x)∎
\end{align*}
$$

**Second part:**


$$ 
\begin{align*}
\sum_{x \in ℕ_a^{b-1}}f(x) = \sum_{x \in ℕ_a^{b-1}}ΔF(x) = 
\end{align*}
$$

$$ 
\begin{align*}
F(a+1) - F(a) + F(a+2) - F(a+1) + …  + F(b) - F(b-1) = \\ 
\end{align*}
$$

$$ 
\begin{align*}
F(b) - F(a) 
\end{align*}
∎
$$

### Conclusion:

Notice the similarity with the second fundamental theorem of calculus. The theorem above states, roughly, that finding the sum of function $f$ over $x \in ℕ_0^{x-1}$ is equivalent to finding a function $F$ such that $ΔF(x) = f(x)$.

We can now answer our original question of how we could systematically find the answer to:

$$ 
\begin{align*}
\sum_{x=0}^{n} x^2 = ? 
\end{align*}
$$

using the fundamental theorem of discrete calculus.
First thing is we would like to find a function $F(x)$ such that $ΔF(x)=x^2$. Let's define a few deltas a then solve for $x^2$.


$$ 
\begin{align*}
Δn = 1 \\ 
Δn^2 = 2n +1 \\ 
Δn^3 = 3n^2 + 3n +1
\end{align*}
$$

Expressing in terms of $Δn$:

$$ 
\begin{align*}
Δn = 1 \\ 
n= \frac{Δn^2 - Δn}{2} \\ 
n^2 = \frac{Δn3}{3} - \frac{Δn^2}{2} + \frac{Δx}{6}
\end{align*}
$$


by linearity of the forward difference operator

$$ 
\begin{align*}
n^2 = \frac{ Δn^3 }{3} - \frac{Δn^2}{2} +\frac{Δn}{6} = Δ(\frac{n^3}{3} - \frac{n^2 }{2} + \frac{n}{6}) = Δ(\frac{2n^3 - 3n^2 + n}{6})
\end{align*}
$$

and thus we have found a function $F(n) = \frac{2n^3 - 3n^2 + n}{6}$ such that $ΔF(n)=n^2$.
Doing some basic algebra we can express our original summation from 

$$ 
\begin{align*}
\sum_{x=0}^{n} x^2  
\end{align*}
$$

using $F(n)$, and since we proved 

$$ 
\begin{align*}
F(n)=\sum_{x \in ℕ_0^{n-1}}f(x)  
\end{align*}
$$

we can show our original equation that we wanted to prove is in fact $F(n+1)$. 
We should get the known closed formula of $\frac{2n^3 + 3n^2 + n}{6}$ mentioned in the beginning.

Let's test it:

$$ 
\begin{align*}
F(n+1) =\sum_{x \in ℕ_0^{n}}f(x) = \frac{2(n+1)^3 -3(n+1)^2 - n+1}{6}\\ \\
= \frac{2(n^3+3n^2+3n+1) -3(n^2+2n+1) + n + 1}{6}\\ 
\frac{2n^3 + 6n^2 + 6n + 2 - 3n^2 - 6n - 3 + n + 1}{6}= \frac{2n^3 + 3n^2 +n}{6} 
\end{align*}
$$


which is exactly the formula we wanted.
We can use the fundamental theorem of discrete calculus find closed formulas for sums of polynomials with even higher degrees.

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
