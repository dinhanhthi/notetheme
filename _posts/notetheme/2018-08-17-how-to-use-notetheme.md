---
title: How to use NoteTheme
categories: [notetheme]
tags: [jekyll,theme,notetheme]
maths: 1
toc: 1
comment: 1
datacamp: 1
---

In this tutorial, I suppose that you have already [installed notetheme]({{ site.baseurl }}/how-to-install-notetheme), just follow the ones you need and don't forget to leave a comment below.

{% include tip.html content="I'm not a native English speaker, please ignore my bad expressions." %}

{% include toc.html %}

## Front Matter

Begin of each post, you need to be careful to choose the right [front matter](https://jekyllrb.com/docs/frontmatter/) for that post. What's front matter? Something like this

~~~ {%raw%}
---
layout: post
title: How to use NoteTheme?
---
{% endraw %} ~~~

There are some already-defined components on NoteTheme that you could use (If you don't want to use something, **remember to REMOVE it**)

- `maths: 1` add this if you wanna use mathematical expression in the post.
- `toc: 1` if you wanna display table of contents on the left sidebar
- `comment: 1` if you wanna use disqus comment system for this post
- `datacamp: 1` if you wanna use datacamp light
- `categories: [notetheme,jekyll]` add category you want
- `tags: [notetheme,jekyll,code]` add tag you want
- `date: 2018-08-21` if you update the post, write the updated date


## Insert codes

### Syntax highlighting

<div class="row d-flex" markdown="1">
<div class="col s12 l6" markdown="1">

You can insert any block of code you want with a syntax highlight effect like below

Available languages : `ruby`, `python`, `c`, `matlab`, `latex`, `html`, `css`, `javascript`.

~~~ {%raw%}
{% highlight ruby %}

{% endhighlight %}
{% endraw %} ~~~
</div>
<div class="col s12 l6" markdown="1">
For example, **Python** with **line numbering**,

~~~ {%raw%}
{% highlight python linenos %}

{% endhighlight %}
{% endraw %} ~~~
</div>
</div>

<div class="row d-flex" markdown="1">
<div class="col s12 l6" markdown="1">
or something appears in the command line window like this
<div class="terminal" markdown="1">
`$ sudo apt-get update`
</div>
</div>
<div class="col s12 l6" markdown="1">
by using
~~~ html
<div class="terminal" markdown="1">
`$ sudo apt-get update`
</div>
~~~
</div>
</div>


### Insert liquid code

- If you wanna add tag `{{"{% this "}}%}`, use `{% raw %}{{"{% this "}}%}{% endraw %}`.
- If you like this `{{"{{ this "}}}}`, use `{% raw %}{{"{{ this "}}}}{% endraw %}`.
- **The rule**: use `{% raw %}{{"{% endraw %}` before the key-word and end with `{% raw %}"}}{% endraw %}` before the end of key-word.
- **An easier way**: use `{{ "{% raw " }}%}` and `{{ "{% endraw " }}%}` around the key-word. These two commands are also used for a block of codes, 

	~~~
	~~~ {{ "{% raw " }}%}{% raw %}{% for %}
	// các dòng codes
	{% end for %}{% endraw %}{{ "{% endraw " }}%} ~~~
	~~~

	**Tips**: For a beautiful display, put `{{ "{% raw " }}%}` and `{{ "{% endraw " }}%}` exactly like the above code.

### Keyboard

You can also insert a keyboard like this <kbd>Ctrl</kbd> + <kbd>B</kbd>, just use `<kbd>Ctrl</kbd>`.


## Insert DataCamp R/Python code environment

- In sert in **Front matter** of the post you wanna insert DataCamp Light: `datacamp: 1`
- [Read more about datacamp light](https://github.com/datacamp/datacamp-light)
- **Example**

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

- **Block of codes**

	~~~ html
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
	~~~

- **Explanation**
	- `data-lang="r"`: language to choose, `r` or `python`
	- `pre-exercise-code`: load before executing.
	- `sample-code`: These will appear in the text editor (left side)
	- `solution`: The solution of the exercise
	- `sct`: Check and give the results, see more for [R](https://github.com/datacamp/testwhat) and [python](https://github.com/datacamp/pythonwhat).



## Insert figure

### Insert in a normal way

~~~ {% raw %}
![](/link/to/figure/){:.w-500 .no-border}
{% endraw %} ~~~

<div class="thi-colums" markdown="1">
- `no-border`: remove the border around figure
- `w-300`: reduce the size of image to maximum `300px` (if the screen's maximum size is `500px`, the figure's size will be `100%` the size of the screen). You can change the number `3` in `300` by other numbers `2,4,5,6,7,8,10` or something like `w-150`.
</div>

### Insert an inline figure

~~~ {% raw %}
{% include img-inline.html content="/link/to/figure/" %}
{% endraw %} ~~~

## Insert an video from Youtube

Determine the youtube video's url, like this

~~~
https://www.youtube.com/watch?v=wIsK4kQTrIg
~~~

Choose `wIsK4kQTrIg` and put it inside below code

~~~ {% raw %}
{% include youtube.html content="wIsK4kQTrIg" size="5" %}
{% endraw %} ~~~

In that, `5` represents the percent your youtube container width in comparison with the page's width, for example, `5` means "50%". You can choose any integer number between `3` and `10`. This size is only available on a wide screen (min width is 993px), when the screen is smaller than 993px, the width becomes automatically 100% of page width.

## For writing posts

### Remove heading numbering

If you don't want display number before some heading, just put BEFORE this heading `{.nocount}`, for example,

~~~ {% raw %}
{:.nocount}
## Heading without numbering
{% endraw %} ~~~

If you wanna use multiple classes, separate them by space.

### Manually assign an id for a heading

Indert `{:#your-id}` before this heading, for instance,

~~~ {% raw %}
{:#your-id}
## Heading
{% endraw %} ~~~

If you wanna use it,

~~~ {% raw %}
[Caption]({{ post.url }}#your-id)
{% endraw %} ~~~

### Insert toc (table of contents)

Insert this line

~~~ {% raw %}
{% include toc.html %}
{% endraw %} ~~~

### Insert heading only on toc (not display it on the post)

Use the class `notdisplay`,

~~~ {% raw %}
{:.notdisplay}
# Hidden deading
{% endraw %} ~~~

### Make columns for a list

Put the list inside a `<div>` tag like,

{% highlight html %}
<div class="thi-columns" markdown="1">
- item 1
- item 2
- item 3
- item 4
- item 5
- item 6
</div>
{% endhighlight %}

Results,

<div class="thi-columns" markdown="1">
- item 1
- item 2
- item 3
- item 4
- item 5
- item 6
</div>

### Make side-by-side code and result

{% highlight html %}
<div class="row d-flex" markdown="1">
<div class="col s12 l6" markdown="1">
~~~
This is the code
~~~
</div>
<div class="col s12 l6" markdown="1">
~~~
This is the result
~~~
</div>
</div>
{% endhighlight %}

gives

<div class="row d-flex" markdown="1">
<div class="col s12 l6" markdown="1">
~~~
This is the code
~~~
</div>
<div class="col s12 l6" markdown="1">
~~~
This is the result
~~~
</div>
</div>

You can change the value of `5` and `6` by other numbers depending on the ratio between their size (their sum must be equal to `11`). Read more on the [grid of materialize](http://next.materializecss.com/grid).


### Insert a read-more link

<div class="row d-flex" markdown="1">
<div class="col s12 l6" markdown="1">

~~~ {% raw %}
{% include more.html content="[Welcome to Math2IT](http://math2it.com)." %}
{% endraw %} ~~~

</div>
<div class="col s12 l6" markdown="1">

{% include more.html content="[Welcome to Math2IT](http://math2it.com)." %}

</div>
</div>


### Insert steps

<div class="row d-flex" markdown="1">
<div class="col s12 l6" markdown="1">

If you want something like this,

<div  class="thi-step">
<div class="step">
<div class="step-number">
</div>
<div class="step-content" markdown="1">
Content in step 1.
</div>
</div>

<div class="step">
<div class="step-number">
</div>
<div class="step-content" markdown="1">
Content in step 2
</div>
</div>
</div>

</div>
<div class="col s12 l6" markdown="1">

Use below codes,

~~~ html
<div  class="thi-step">
<div class="step">
<div class="step-number"></div>
<div class="step-content" markdown="1">
Content in step 1.
</div>
</div>

<div class="step">
<div class="step-number"></div>
<div class="step-content" markdown="1">
Content in step 2
</div>
</div>
</div>
~~~

</div>
</div>


## Mathematical expressions

- Inline math, use `$math-expression$`
- Block of math, use `$$math block$$` or 

	~~~ latex
	$$
	x^n + y^n = z^n
	$$
	~~~

- If you wanna insert some special characters, you must put `\` before this character, for instance, `\\{ 1,2,3 \\}` gives $\\{ 1m2,3 \\}$
- If you type inline maths which contain chatacters `_`, you must add `\` before each of them, for example, `a\_1` give $a\_1$.
- Don't use `||` for absolute values, let's use `\vert \vert` instead.
- Don't use `\left\| \right\|` for norms, use `\Vert \Vert` instead.
- Don't use `*` for star symbols, use `\ast` instead.
- If you wanna type `\\`, type `\\\\` instead.
- If you wanna type an inline matrix, e.g., $[A]=\begin{bmatrix}1 & 2 \\\\ 2 & 3.999 \end{bmatrix}$, type like below,

	~~~ latex
	$[A]=\begin{bmatrix}1 & 2 \\\\ 2 & 3.999 \end{bmatrix},$
	~~~

- In order to use `\label{}` and `\eqref{}` like in latex, use

	~~~ latex
	$$
	\begin{align}\tag{1}\label{eq1}
	x^n + y^n = z^n
	\end{align}
	$$
	
	Call again equation $\eqref{eq1}$.
	~~~

	which gives

	$$
	\begin{align}\tag{1}\label{eq1}
	x^n + y^n = z^n
	\end{align}
	$$

	Call again equation $\eqref{eq1}$.

- You don't need an enviroment `align` or `equation` to use `\label`, you can use it with `$$` only, for example,

	~~~ latex
	$$
	x^n + y^n = z^n \tag{1}\label{eq1}
	$$
	
	Call again equation $\eqref{eq1}$.
	~~~


## Boxes

### Theorem boxes

<div class="row d-flex" markdown="1">
<div class="col s12 l6" markdown="1">

Use these lines of code

{% highlight html %}
<div class="thi-box" markdown="1">
<div class="box-title" markdown="1">
**Title**
</div>
<div class="box-content" markdown="1">
Content
</div>
</div>
{% endhighlight %}

</div>
<div class="col s12 l6" markdown="1">

which give

<div class="thi-box" markdown="1">
<div class="box-title" markdown="1">
**Title**
</div>
<div class="box-content" markdown="1">
Content
</div>
</div>

</div>
</div>


### Notification boxes

<div class="row d-flex" markdown="1">
<div class="col s12 l8" markdown="1">

Use these lines of code

~~~ {% raw %}
{% include warning.html content="Warning's content" %}
{% endraw %} ~~~

</div>
<div class="col s12 l4" markdown="1">

which give

{% include warning.html content="Warning's content" %}

</div>
</div>

<div class="row d-flex" markdown="1">
<div class="col s12 l8" markdown="1">

Use these lines of code

~~~ {% raw %}
{% include tip.html content="Info's content" %}
{% endraw %} ~~~

</div>
<div class="col s12 l4" markdown="1">

which give

{% include tip.html content="Info's content" %}

</div>
</div>



### Insert hide/show box

<div class="row d-flex" markdown="1">
<div class="col s12 l6" markdown="1">

Use these lines of code

~~~ html
<ul class="collapsible" data-collapsible="accordion">
<li>
<div class="collapsible-header" markdown="1"><i class="material-icons">face</i>
Title
</div>
<div class="collapsible-body" markdown="1">
Content
</div>
</li>
</ul>
~~~

</div>
<div class="col s12 l6" markdown="1">

which give

<ul class="collapsible" data-collapsible="accordion">
<li>
<div class="collapsible-header" markdown="1"><i class="material-icons">face</i>
Title
</div>
<div class="collapsible-body" markdown="1">
Content
</div>
</li>
</ul>

</div>
</div>


### Insert blockquote

<p class="post-more-info" markdown="1">
The content of extra info of the post.
</p>

{% highlight html %}
<p class="post-more-info" markdown="1">
The content of extra info of the post.
</p>
{% endhighlight %}

> Other normal blockquote like this.

### Insert resume of the post

<div class="row d-flex" markdown="1">
<div class="col s12 l6" markdown="1">

Use these lines of code

{% highlight html %}{%raw%}
<fieldset class="field-set" markdown="1">
<legend class="leg-title">Title</legend>
Content
</fieldset>
{%endraw%}{% endhighlight %}

</div>
<div class="col s12 l6" markdown="1">

which give

<fieldset class="field-set" markdown="1">
<legend class="leg-title">Title</legend>
Content
</fieldset>

</div>
</div>


{:#cat-tag}
## Categories and tags

### Use it

On the front matter of each post, use this

~~~
categories: [maths, python] 
tags: [algebra, function, theorem]
~~~

### Create a new category

1. Below the title of each post, you will see "in <category>", for example, this post **in NoteTheme**.
2. Open file `_data\categories.yml` and add the new category you want
	- `slug`: the id of this category, it will appear in the url, like
		~~~
		https://dinhanhthi.github.io/notetheme/categories#notetheme
		~~~
	- `name` : the name of this catefory, it will appear on the site, like `notetheme`

### Already-defined tags / categories

Already-defined categories:

<div class="thi-columns">
<ul>
{% for cat in site.data.categories %}
<li><code class="highlighter-rouge">{{ cat.slug }}</code> : <a href="/{{cat.slug}}">{{ cat.name }}</a></li>
{% endfor %}
</ul>
</div>

<p>
Already-defined tags: 
{% for tag in site.tags %}
<code class="highlighter-rouge">{{ tag[0] }}</code>
{% if forloop.last == false %}
, 
{% else %}
.
{% endif %}
{% endfor %}
</p>