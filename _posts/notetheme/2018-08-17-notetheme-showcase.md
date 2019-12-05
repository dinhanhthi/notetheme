---
title: Some showcases with NoteTheme
categories: [notetheme]
tags: [jekyll,theme,notetheme]
maths: 1
toc: 1
comment: 1
datacamp: 1
---

In this post, I will show you all of alread-defined components in NoteTheme so that you can use it in the fugure. If you have interests on some components, jut read **[how to make it]({{ site.baseurl }}/how-to-use-notetheme)**.

{% include tip.html content="I'm not a native English speaker, please ignore my bad expressions." %}

<fieldset class="field-set" markdown="1">
<legend class="leg-title">TL;DR</legend>

- Show the post in a flexible way.
- Show the figures any place
- Show the maths, the code blocks in a beautiful way.
- and many things else...

</fieldset>

> A bloquequote will display like this. You can also use [all designed components](https://materializecss.com/) from Materialize if you want.



## Insert code & figures

<div class="row d-flex" markdown="1">
<div class="col s12 l6" markdown="1">

You can insert any code you want with the syntax highlight like below

~~~ latex
\documentclass[12pt,a4paper]{article}
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
\usepackage{graphicx}
\usepackage[left=2cm,right=2cm,top=2cm,bottom=2cm]{geometry}
 
\begin{document}

This is an example of \LaTeX document, but you can use other language like C++, Python, Matlab,...

\end{document}
~~~

</div>
<div class="col s12 l6" markdown="1">

or something appears in the command line windows like this

<div class="terminal">
$ sudo apt-get update
</div>

</div>
</div>


You can even couple inseting a code block with a side-by-side figure like this

<div class="row d-flex" markdown="1">
<div class="col s12 l6" markdown="1">
~~~ python
import matplotlib.pyplot as plt
plt.plot(year,pop)
plt.show()
~~~
</div>
<div class="col s12 l6" markdown="1">

![]({{ site.baseurl }}/images/posts/f1.svg){:.w-400 .no-border}

</div>
</div>

<div class="row d-flex" markdown="1">
<div class="col s12 l6" markdown="1">

![]({{ site.baseurl }}/images/posts/dog.png){:.w-300 .no-border}

</div>
<div class="col s12 l6" markdown="1">

... or something like this, but on the right! 

**Oh, I'm a very small dog <img class="img-inline" src="{{ site.baseurl }}/images/posts/dog-inline.png" />  and I'm inline text.**

</div>
</div>

## How about Youtube video?

You can insert any size of youtube container on the large screen,

{% include youtube.html content="8f7eSJOHeYY" size="8" %}

... or with smaller one

{% include youtube.html content="8f7eSJOHeYY" size="4" %}

## Make an interactive coding course online

You even can embed **R/Python** code environment inside a post like this

<div class="mt-2 mb-2" data-datacamp-exercise data-lang="r">
	<code data-type="pre-exercise-code">
		# This will get executed each time the exercise gets initialized
		b = 6
	</code>
	<code data-type="sample-code">
		# Create a variable a, equal to 5
		# Print out a
	</code>
	<code data-type="solution">
		# Create a variable a, equal to 5
		a <- 5

		# Print out a
		print(a)
	</code>
	<code data-type="sct">
		test_object("a")
		test_function("print")
		success_msg("Great job!")
	</code>
	<div data-type="hint">Use the assignment operator (<code><-</code>) to create the variable <code>a</code>.</div>
</div>


{% include toc.html %}

## Play with content

<div class="thi-columns" markdown="1">
- [How to use NoteTheme?]({{site.baseurl}}/how-to-use-notetheme)
- [Welcome to NoteTheme]({{site.baseurl}}/welcome-to-notetheme)
- [How to install NoteTheme]({{site.baseurl}}/how-to-install-notetheme)
- [Math2IT facebook fanpage](https://facebook.com/Math2IT)
- [Math2IT official website](http://math2it.com)
- [Math2IT group on facebook](https://www.facebook.com/groups/math2it/)
- [Đinh Anh Thi's personal website](http://dinhanhthi.com)
</div>

It will automatically become 1 colum if you see this post on a small screen device.

{% include tip.html content="You can see that, you can put the table of contetnt in any place in the post." %}

If you have something too long and need to hide it in default, you can put it inside a hide/show box like this

<ul class="collapsible" data-collapsible="accordion">
<li>
<div class="collapsible-header" markdown="1"><i class="material-icons">face</i>
Click me to open the secret
</div>
<div class="collapsible-body" markdown="1">
This is a very long content without meaning. This is a very long content without meaning. This is a very long content without meaning. This is a very long content without meaning. This is a very long content without meaning. This is a very long content without meaning. This is a very long content without meaning. This is a very long content without meaning. This is a very long content without meaning.
</div>
</li>
</ul>

{% include warning.html content="Don't foget to share this theme with your friends!" %}



## For mathematicians

You can easily insert a math inside a post,

$$
\begin{align}\tag{1}\label{eq1}
\begin{cases}
x + 3y - z &= 5 \\
2x +3z &= 7 \\
y - 4z &= 8 
\end{cases}
\end{align}
$$

You can even call $\eqref{eq1}$ again another place if you want.

<div class="thi-box" markdown="1">
<div class="box-title" markdown="1">
**For a Theorem? No problem!**
</div>
<div class="box-content" markdown="1">

You have a very beautiful box for describing a theorem or definition.

</div>
</div>

## How can you make a post like this?

<p class="post-more-info" markdown="1">
If you need something more, just let me know in the comment below this post!
</p>

<div  class="thi-step">
<div class="step">
<div class="step-number">
</div>
<div class="step-content" markdown="1">
Download [this theme](https://github.com/dinhanhthi/notetheme).
</div>
</div>

<div class="step">
<div class="step-number">
</div>
<div class="step-content" markdown="1">
Read [this link]({{site.baseurl}}/how-to-install-notetheme) to know how to install it and create a new website for yourself.
</div>
</div>

<div class="step">
<div class="step-number">
</div>
<div class="step-content" markdown="1">
Follow [this link]({{site.baseurl}}/how-to-use-notetheme) to make an awesome post like this one.
</div>
</div>
</div>

Just use <kbd>Ctrl</kbd> + <kbd>C</kbd> to copy and paste shortcodes defined in NoteTheme.

{% include more.html content="[Thank you and let's start!](https://dinhanhthi.github.io/NoteTheme/welcome-to-notetheme)." %}
