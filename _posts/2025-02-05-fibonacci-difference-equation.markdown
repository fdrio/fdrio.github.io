---
layout: post
title: "The Golden Ratio and Fibonacci Numbers"
date: 2025-02-05 10:00:00 +0000
categories: [category1, category2]
tags: [tag1, tag2]
---
{%- include mathjax.html -%}
![Fern](/assets/images/fibonacci-difference-equation/unfurling-fern-leigh-henningham.jpg)

The Fibonacci numbers $F(t)$, $t= 1,2,3,…$ are defined recursively by 

$$ 
\begin{align*}
F(t+2) = F(t+1) + F(t) , \qquad t∈ℕ_1 
\end{align*}
$$

with the given initial conditions

$$ 
\begin{align*}
F(1) = 1 = F(2)
\end{align*}
$$

The Fibonacci sequence is given by 

$$ 
\begin{align*}
1, 2, 3, 5, 8, 13, 21, 34
\end{align*}
$$

Fibonacci used this to model the population of pairs rabbits under certain assumptions. To find $F(t)$, note that $F(t)$ is the solution of the initial value problem (IVP)

$$ 
\begin{align*}
Δ^2F(t) + ΔF(t) - F(t) = 0, \qquad t∈ℕ_1
\end{align*}
$$

Where $Δ$ is the discrete rate of change called the forward difference operator defined below

$$ 
\begin{align*}
F: ℕ_a^b → ℝ, \qquad ΔF(t) \:= F(t+1) - F(t) \qquad t ∈ ℕ_a^{b-1} \\ 
\end{align*}
$$

$$ 
\begin{align*}
F(1) = 1 = F(2)
\end{align*}
$$

One way of solving this, is rewriting the difference equation as 

$$ 
\begin{align*}
Δ^2F(t) + ΔF(t) - F(t) = 0, \qquad t∈ℕ_1  \\ 
\end{align*}
$$

$$ 
\begin{align*}
= [λ_i^2 + λ_i -1] e_{λ_i}(t,s) = 0.
\end{align*}
$$

where $e_{p(t)}(t,s)$ is defined as: 


$$ 
\begin{align*}
 e_{p(t)}(t,s)=
\begin{cases} 
    \prod_{τ=1}^{t-1} [1+p(τ)], & \text{if } t ∈ ℕ_s \\
    \prod_{τ=t}^{s-1} \frac{1}{1+p(τ)}, & \text{if } t ∈ ℕ_a^{s-1} \\
\end{cases}
\end{align*}
$$

given $p(t) ∈ ℛ$, where is $ℛ$ is the set of regressive functions defined as

$$ 
\begin{align*}
ℛ= \{p(t): ℕ_a → ℝ ∣ 1  + p(t)  ≠ 0, ∀t∈ℕ_a \}
\end{align*}
$$


and $e_{p(t)}(t,s)$ has the following property

$$ 
\begin{align*}
Δe_{p(t)}(t,s) = p(t)e_{p(t)}(t,s)
\end{align*}
$$

To solve the IVP we first get that the characteristic equation is 
$$ 
\begin{align*}
λ^2 + λ - 1 = 0
\end{align*}
$$

Hence, the characteristic values are 

$$ 
\begin{align*}
λ_1 = \frac{-1 + \sqrt{5}}{2}, \qquad λ_2 = \frac{-1 - \sqrt{5}}{2}
\end{align*}
$$


Since the two solutions are linearly independent on $ℕ_1$, it follows that

$$ 
\begin{align*}
F(t) = c_1 e_{λ_1}(t,1) + c_2 e_{λ_2}(t,1)  
\end{align*}
$$

$$ 
\begin{align*}
= c_1\Bigg(\frac{1+\sqrt{5}}{2}\Bigg)^{t-1}+c_2\Bigg(\frac{1 - \sqrt{5}}{2}\Bigg)^{t-1}
\end{align*}
$$


Applying the initial conditions we get 

$$ 
\begin{align*}
F(1) = 1 = c_1+c_2
\end{align*}
$$


$$ 
\begin{align*}
F(2) = 1 = c_1\Bigg(\frac{1+\sqrt{5}}{2}\Bigg)+c_2\Bigg(\frac{1 - \sqrt{5}}{2}\Bigg)
\end{align*}
$$


Now, solve to find the values for $c_1$ and $c_2$

$$ 
\begin{align*}
c_1+c_2 = 1 → c_1 = 1-c_2\\ \\
c_1\Bigg(\frac{1+\sqrt{5}}{2}\Bigg)+c_2\Bigg(\frac{1 - \sqrt{5}}{2}\Bigg) = 1 \\ \\
(1 - c_2)\Bigg(\frac{1+\sqrt{5}}{2}\Bigg)+c_2\Bigg(\frac{1 - \sqrt{5}}{2}\Bigg) = 1 \\ \\
(1 - c_2)\Bigg(\frac{1+\sqrt{5}}{2}\Bigg)+c_2\Bigg(\frac{1 - \sqrt{5}}{2}\Bigg) = 1 \\ \\
\Bigg(\frac{1+\sqrt{5}}{2}\Bigg) - c_2 \Bigg(\frac{1+\sqrt{5}}{2}\Bigg) + c_2\Bigg(\frac{1 - \sqrt{5}}{2}\Bigg) = 1 \\ \\
c_2 \Bigg[-\Bigg(\frac{1+\sqrt{5}}{2}\Bigg) + \Bigg(\frac{1 - \sqrt{5}}{2}\Bigg)\Bigg] = 1 - \Bigg(\frac{1+\sqrt{5}}{2}\Bigg) \\ \\
 -\sqrt{5}c_2 = \Bigg(\frac{1 - \sqrt{5}}{2}\Bigg) \\ \\ 
 c_2 = \frac{-1}{\sqrt{5}}\Bigg(\frac{1 - \sqrt{5}}{2}\Bigg) 
\end{align*}
$$

Now to get $c_1$

$$ 
\begin{align*}
c_1+c_2 = 1 → c_1 = 1-c_2\\ \\
 c_1 = 1- \frac{-1}{\sqrt{5}}\Bigg(\frac{1 - \sqrt{5}}{2}\Bigg) \\ \\
 c_1 = \frac{1}{\sqrt{5}}\Bigg(\sqrt{5} + \frac{1 - \sqrt{5}}{2}\Bigg) \\ \\
 c_1 = \frac{1}{\sqrt{5}}\Bigg(\sqrt{5} + \frac{1 - \sqrt{5}}{2}\Bigg) \\ \\
 c_1 = \frac{1}{\sqrt{5}}\Bigg(\frac{1 + \sqrt{5}}{2}\Bigg) \\ \\
\end{align*}
$$

Thus 

$$ 
\begin{align*}
F(t) = \frac{1}{\sqrt{5}}\Bigg(\frac{1 + \sqrt{5}}{2}\Bigg)^{t} - \frac{1}{\sqrt{5}}\Bigg(\frac{1 - \sqrt{5}}{2}\Bigg)^{t}
\end{align*}
$$

**Conclusion**  
In summary, we have shown that the solution to the Fibonacci difference equation, subject to the specified initial conditions, can be written in closed form as the **Binet's formula**:

$$ 
\begin{align*}
F(t) \;=\; \frac{1}{\sqrt{5}}\biggl(\frac{1 + \sqrt{5}}{2}\biggr)^{t} \;-\; \frac{1}{\sqrt{5}}\biggl(\frac{1 - \sqrt{5}}{2}\biggr)^{t}.
\end{align*}
$$


Since the second term in the formula decays rapidly towards zero for large $t$, we obtain the following approximation:

$$ 
\begin{align*}
F(t) \approx \frac{1}{\sqrt{5}} \biggl(\frac{1+\sqrt{5}}{2}\biggr)^t.
\end{align*}
$$

This formula explicitly expresses $F(t)$ in terms of the two characteristic roots,  

$$ 
\begin{align*}
\frac{-1 + \sqrt{5}}{2} \quad \text{and} \quad \frac{-1 - \sqrt{5}}{2},
\end{align*}
$$
  
which are related to the *golden ratio* 

$$ 
\begin{align*}
ϕ \;=\; \frac{1 + \sqrt{5}}{2}.
\end{align*}
$$

Consequently, the Fibonacci sequence at step $t$ is a function of powers of the golden ratio (and its conjugate). This reveals the deep connection between the Fibonacci sequence and $ϕ$, a constant that appears in many contexts spanning mathematics, art, and nature.




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
