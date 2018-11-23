---
title: Shortcuts for editors
categories: [it]
tags: [jekyll,notetheme]
maths: 1
toc: 1
snippet: 1
date: 2018-10-08
---

This post is only for editors, please read other posts.

{% include toc.html %}

## Front Matter

There are some already-defined components on NoteTheme that you could use (If you don't want to use something, **remember to REMOVE it**)

- `maths: 1` add this if you wanna use mathematical expression in the post.
- `toc: 1` if you wanna display table of contents on the left sidebar
- `comment: 1` if you wanna use disqus comment system for this post
- `datacamp: 1` if you wanna use datacamp light
- `categories: [notetheme,jekyll]` add category you want
- `tags: [notetheme,jekyll,code]` add tag you want
- `date: 2018-08-21` if you update the post, write the updated date
- `snippet: 1` if you want to pin this post to the Snippets section.
- `bigimg`: background photo of the post (showing on shared post on facebook)

## Texts

- **New** badge: `<new />`
- **Update** bagge: `<update />`
- **Keyboard**: `<kbd>Ctrl</kbd>`

## Codes

### Insert liquid code

- If you wanna add tag `{{"{% this "}}%}`, use `{% raw %}{{"{% this "}}%}{% endraw %}`.
- If you like this `{{"{{ this "}}}}`, use `{% raw %}{{"{{ this "}}}}{% endraw %}`.
- **The rule**: use `{% raw %}{{"{% endraw %}` before the key-word and end with `{% raw %}"}}{% endraw %}` before the end of key-word.
- **An easier way**: use `{{ "{% raw " }}%}` and `{{ "{% endraw " }}%}` around the key-word. These two commands are also used for a block of codes, 

  ~~~
  ~~~ {{ "{% raw " }}%}{% raw %}{% for %}
  // line of codes
  {% end for %}{% endraw %}{{ "{% endraw " }}%} ~~~
  ~~~

	**Tips**: For a beautiful display, put `{{ "{% raw " }}%}` and `{{ "{% endraw " }}%}` exactly like the above code.

## Figures / Tables / Videos

- **Normal way**

  ~~~ {% raw %}
  ![](/link/to/figure/){:.w-500 .no-border}
  {% endraw %} ~~~

- **Inline figures**

  ~~~ {% raw %}
  {% include img-inline.html content="/link/to/figure/" %}
  {% endraw %} ~~~

- **Youtube video**

  ~~~ {% raw %}
  {% include youtube.html content="wIsK4kQTrIg" size="5" %}
  {% endraw %} ~~~


## Boxes

### Hide/Show

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

### Notifications

- Info

  ~~~ html
  <p markdown="1" class="thi-tip">
  <i class="material-icons mat-icon">info</i>
  content
  </p>
  ~~~

- Error

  ~~~ html
  <p markdown="1" class="thi-warning">
  <i class="material-icons mat-icon">error</i>
  content
  </p>
  ~~~


### Pull quotes

~~~ html
<p class="post-more-info" markdown="1">
The content of extra info of the post.
</p>
~~~

### Summarization box

~~~ html
<fieldset class="field-set" markdown="1">
<legend class="leg-title">Title</legend>
Content
</fieldset>
~~~

### Theorem style

~~~ html
<div class="thi-box" markdown="1">
<div class="box-title" markdown="1">
**Title**
</div>
<div class="box-content" markdown="1">
Content
</div>
</div>
~~~

### Important boxes

~~~ html
<div class="p-mark" markdown="1">
Content
</div>
~~~

## Others

### Add toc

~~~ {% raw %}
{% include toc.html %}
{% endraw %} ~~~

### Columns for lists

~~~{% raw %} html
<div class="thi-columns" markdown="1">
- item 1
- item 2
- item 3
- item 4
- item 5
- item 6
</div>
{% endraw %}~~~

### Side by side

~~~ html
<div class="row d-flex" markdown="1">
<div class="col s12 l6" markdown="1">
This is the code
</div>
<div class="col s12 l6" markdown="1">
This is the result
</div>
</div>
~~~

### Links

See again

~~~ html
<div class="see-again">
<i class="material-icons">settings_backup_restore</i>
<span markdown="1">
Content
</span>
</div>
~~~

Read-more link

~~~ {% raw %}
{% include more.html content="[Welcome to Math2IT](http://math2it.com)." %}
{% endraw %} ~~~

Download

~~~ {% raw %}
{% include download.html content="[Download text](download link)." %}
{% endraw %} ~~~

### Steps

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
