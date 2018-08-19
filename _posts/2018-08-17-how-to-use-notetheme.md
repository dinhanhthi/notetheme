---
title: How to use NoteTheme
categories:
  - it
maths: 1
toc: 1
comment: 1
---

{% include toc.html %}

## Chèn code

### Highlight cho code

Có các ngôn ngữ : `ruby`, `python`, `c`, `matlab`, `latex`, `html`, `css`, `javascript`.

~~~ {%raw%}
{% highlight ruby %}

{% endhighlight %}
{% endraw %} ~~~

Python với **đánh số dòng**:
~~~ {%raw%}
{% highlight python linenos %}

{% endhighlight %}
{% endraw %} ~~~

### Chèn code liquid

- Nếu muốn thêm tag `{{"{% this "}}%}` thì ghi `{% raw %}{{"{% this "}}%}{% endraw %}`.
- Còn nếu muốn thêm `{{"{{ this "}}}}` thì ghi `{% raw %}{{"{{ this "}}}}{% endraw %}`.

Quan trọng là mở đầu bằng `{% raw %}{{"{% endraw %}` trước từ khóa và kết thúc bằng `{% raw %}"}}{% endraw %}` trước kết thúc từ khóa.

Hoặc một cách khác dễ hơn, đó là dùng `{{ "{% raw " }}%}` và `{{ "{% endraw " }}%}` bao quanh từ khóa cần hiện. Hai từ này còn có thể dùng để hiện một đoạn code nếu được đặt trước đó.

~~~
~~~ {{ "{% raw " }}%}{% raw %}{% for %}
// các dòng codes
{% end for %}{% endraw %}{{ "{% endraw " }}%} ~~~
~~~

Lưu ý, để cho khung code đẹp, bạn nên đặt `{{ "{% raw " }}%}` và `{{ "{% endraw " }}%}` giống như đoạn code mẫu trên.

## Chèn hình

### Chèn bình thường

~~~ {% raw %}
![](/images/posts/toan-so-cap/){:.w-500 .no-border}
{% endraw %} ~~~

<div class="thi-colums" markdown="1">
- `no-border`: bỏ đi khung bao quanh hình
- `w-300`: giảm kích thước hình về tối đa `300px` (với màn hình có chiều ngang tối đa `500px` thì sẽ chuyển về `100%` kích thước màn hình). Có thể thay số `3` trong `300` bởi `2,4,5,6,7,8,10` hoặc `w-150`.
</div>

### Chèn hình inline

~~~ {% raw %}
{% include img-inline.html content="đường/dẫn/đến/hình" %}
{% endraw %} ~~~

## Chèn video

Để chèn video từ youtube, bạn tìm trong đường link của video, ví dụ

~~~
https://www.youtube.com/watch?v=wIsK4kQTrIg
~~~

bạn chọn `wIsK4kQTrIg` để thêm vào nội dung của đoạn code sau

~~~ {% raw %}
{% include youtube.html content="wIsK4kQTrIg" %}
{% endraw %} ~~~

## Tags

Front matter

~~~ 
tags: [thu nghiem, analsys, theorem]
~~~

## Soạn thảo

### Bỏ đánh số một heading

Nếu bạn muốn bỏ đánh số một headings nào đó, bạn chỉ việc thêm vào NGAY TRƯỚC heading ấy `{.nocount}`, ví dụ

~~~ {% raw %}
{:.nocount}
## Heading không có đánh số
{% endraw %} ~~~

Nếu bạn muốn dùng nhiều class thì các class cách nhau bởi khoảng trắng (space).

### Gán một id cho heading

Nếu bạn muốn gán một id cho heading nào đó mà không muốn nó tự động được tạo thì bạn thêm `{#id-cua-ban}` vào NGAY TRƯỚC heading đó, ví dụ

~~~ {% raw %}
{:#id-cua-ban}
## Thêm heading
{% endraw %} ~~~

Đến khi bạn muốn gọi lại nó thì dùng

~~~ {% raw %}
[Caption]({{ page.url }}#id-cua-ban)
{% endraw %} ~~~

### Thêm mục lục

Thêm dòng code sau vào **đoạn thứ hai** trong văn bản.

~~~ {% raw %}
{% include toc.html %}
{% endraw %} ~~~

### Thêm headings nhưng không hiện nó ra, chỉ hiện ở toc

Để ẩn một cái gì đó, dùng class `notdisplay`. Nếu muốn ẩn heading nào đó thì dùng

~~~ {% raw %}
{:.notdisplay}
# heading ẩn
{% endraw %} ~~~

### Chia cột cho danh sách

Đặt danh sách trong thẻ `<div>` như sau

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

Kết quả

<div class="thi-columns" markdown="1">
- item 1
- item 2
- item 3
- item 4
- item 5
- item 6
</div>

### Chia cột (code va kết quả)

{% highlight html %}
<div class="row" markdown="1">
<div class="col m12 l5" markdown="1">
~~~
this is the code
~~~
</div>
<div class="col m12 l7" markdown="1">
~~~
this is the result
~~~
</div>
</div>
{% endhighlight %}

Kết quả

<div class="row" markdown="1">
<div class="col m12 l5" markdown="1">
~~~
this is the code
~~~
</div>
<div class="col m12 l7" markdown="1">
~~~
this is the result
~~~
</div>
</div>

Bạn có thể thay đổi giá trị của `5` và `7` tùy theo chênh lệch độ rộng của 2 cột (sao cho tổng là 12 là được). Xem thêm về grid của theme materialize [tại đây](http://next.materializecss.com/grid.html).

### Chèn thêm link đọc thêm

Bạn có thể chèn thêm link đọc thêm dạng

{% include more.html content="[Mời bạn ghé thăm Math2IT](http://math2it.com)." %}

Bạn soạn

~~~ {% raw %}
{% include more.html content="[Mời bạn ghé thăm Math2IT](http://math2it.com)." %}
{% endraw %} ~~~


### Chèn các bước (steps)

Nếu bạn muốn viết bài hướng dẫn với các "steps" như ví dụ dưới đây

<div class="thi-step">
<div class="step" markdown="1">
Nội dung trong bước 1.
</div>
<div class="step" markdown="1">
Nội dung trong bước 2
</div>
</div>

Thì bạn có thể dùng đoạn code sau

{% highlight html %}
<div  class="thi-step">
<div class="step" markdown="1">
Nội dung trong bước 1.
</div>
<div class="step" markdown="1">
Nội dung trong bước 2
</div>
</div>
{% endhighlight %}

Lưu ý, nếu bạn tạo một trang mới không phải là một post bình thường, bạn cần phải để dòng code sau ở YAML đầu trang.

{% highlight html %}
css: "step.css"
{% endhighlight %}


### CSS câu hỏi

Để có thể hiện câu hỏi dạng như sau

{% include question.html content="Nội dung câu hỏi?" %}

Bạn dùng

~~~ {% raw %}
{% include question.html content="Nội dung câu hỏi?" %}
{% endraw %} ~~~

## Soạn thảo toán học

- Trong hàng thì dùng `$cong-thuc-toan$`
- Ngoài hàng thì dùng `$$cong-thuc-toan$$`. Tuy nhiên bạn nên để `cong-thuc-toan` ở một hàng riêng, ví dụ
{% highlight latex %}
$$
cong-thuc-toan
$$
{% endhighlight %}
- Nếu muốn dùng các ký tự đặc biệt, phải để thêm dấu `\` trước nó, ví dụ tập hợp `\\{cac-phan-tu\\}`
- Nếu gõ trong hàng mà có ký tự `_` thì phải thêm `\` trước nó, ví dụ `a\_1`
- Đừng dùng `||` cho giá trị tuyệt đối, mà dùng `\vert \vert`
- Đừng dùng `\left\| \right\|` cho chuẩn, hãy dùng `\Vert \Vert`
- Đừng dùng `*` mà hãy dùng `\ast`
- Gõ `\\` thì dùng `\\\\`

Riêng việc gõ ma trận trong hàng, ví dụ như $[A]=\begin{bmatrix}1 & 2 \\\\ 2 & 3.999 \end{bmatrix},$ thì ta gõ như sau

~~~
$[A]=\begin{bmatrix}1 & 2 \\\\ 2 & 3.999 \end{bmatrix},$
~~~

---

Để có thể `\label` và `\ref` lại công thức toán giống trong LaTeX, bạn gõ như sau

{% highlight latex %}
$$
\begin{align}\tag{1}\label{eq1}
cong-thuc-toan
\end{align}
$$
Gọi lại công thức $\eqref{eq1}$.
{% endhighlight %}

Kết quả giống như sau

$$
\begin{align}\tag{1}\label{eq1}
cong-thuc-toan
\end{align}
$$
Gọi lại công thức $\eqref{eq1}$.

Lưu ý, bạn không cần phải dùng môi trường `align` để có thể sử dụng `label`, bạn dùng như sau vẫn được

{% highlight latex %}
$$
cong-thuc-toan \tag{1}\label{eq1}
$$
Gọi lại công thức $\eqref{eq1}$.
{% endhighlight %}


## Các loại khung

### Thêm box định nghịa, định lý

Bạn dùng đoạn code sau đây

{% highlight html %}
<div class="thi-box" markdown="1">
<div class="box-title" markdown="1">
**Tựa đề**
</div>
<div class="box-content" markdown="1">
Nội dung văn bản
</div>
</div>
{% endhighlight %}

Sẽ cho ra kết quả

<div class="thi-box" markdown="1">
<div class="box-title" markdown="1">
**Tựa đề**
</div>
<div class="box-content" markdown="1">
Nội dung văn bản
</div>
</div>

Lưu ý, nếu có gõ công thức toán học `$$cong-thuc$$` riêng dùng thì nên để 1 hàng trước trước `</div>` gần cuối.

### Thêm các khung thông báo

Để có thể thêm khung cảnh báo như

{% include warning.html content="Nội dung cảnh báo!" %}

Bạn dùng đoạn code

~~~ {% raw %}
{% include warning.html content="Nội dung cảnh báo!" %}
{% endraw %} ~~~

Để có thể thêm khung gợi ý (tip)

{% include tip.html content="Nội dung gợi ý." %}

Bạn dùng

~~~ {% raw %}
{% include tip.html content="Nội dung gợi ý." %}
{% endraw %} ~~~

### Chèn khung hide/show

Vì tạm thời chưa biết cách include một đoạn dài văn bản, bạn dùng cấu trúc dài sau

<ul class="collapsible" data-collapsible="accordion">
<li>
<div class="collapsible-header" markdown="1"><i class="material-icons">face</i>
Tựa đề
</div>
<div class="collapsible-body" markdown="1">
Nội dung
</div>
</li>
</ul>

{% highlight html %}
<ul class="collapsible" data-collapsible="accordion">
<li>
<div class="collapsible-header" markdown="1"><i class="material-icons">face</i>
Tựa đề
</div>
<div class="collapsible-body" markdown="1">
Nội dung
</div>
</li>
</ul>
{% endhighlight %}

Để có thể chèn thêm list vào trong cái collapse này, bạn soạn như sau

{% highlight html %}
<ul class="collapsible" data-collapsible="accordion">
<li>
<div class="collapsible-header" markdown="1"><i class="material-icons">face</i>
Tựa đề
</div>
<div class="collapsible-body" markdown="1">
Văn bản thường
<p markdown="1">
- item 1 <br />
- item 2 <br />
</p>
</div>
</li>
</ul>
{% endhighlight %}

### Khung thông tin đọc thêm cho bài

Nếu bạn muốn thêm thông tin đọc thêm cho bài viết (một ô vuông nhỏ nằm chệch hẳn về bên phải của bài đăng), bạn thêm đoạn code sau đây vào SAU đoạn mà bạn muốn thêm đọc thêm.

{% highlight html %}
<p class="post-more-info" markdown="1">
Nội dung của thông tin thêm.
</p>
{% endhighlight %}

Lưu ý, nếu bạn tạo một trang mới không phải là một post bình thường, bạn cần phải để dòng code sau ở YAML đầu trang.

{% highlight html %}
css: "step.css"
{% endhighlight %}

### Khung tóm tắt nội dung

<fieldset class="field-set">
<legend class="leg-title">Tựa đề</legend>
Nội dung
</fieldset>

{% highlight html %}{%raw%}
{:.tomtat}
### Tóm tắt phần học

<fieldset class="field-set" markdown="1">
<legend class="leg-title">Tựa đề</legend>
Nội dung
</fieldset>
{%endraw%}{% endhighlight %}


{:#cat-tag}
## Categories và tags

### Tạo một category mới

1. Category dùng để hiển thị chủ đề bài viết ở trang chủ (ở góc dưới trái mỗi bài đăng). Nó cũng hiển thị trong mục [Lưu trữ](/categories)
2. Thêm vào `_data\categories.yml`
3. Màu sắc theo quy luật sau
	- **Toán**: `lightcyan` (color), `darkcyan` (txt)
	- **Tin**: `lightyellow` (color), `darkgoldenrod` (txt)
	- **Khám phá**: `"#f0ffdf"` (color), `darkolivegreen` (txt)
	- **Không phân loại**: `"#eceff1"` (color), `darkslategrey` (txt)
4. Thêm file vào `category\`
	- Chỉ thêm file nào khác với `tag` bên dưới!!!
	- Bắt chước cấu trúc các file đang có
	- Tên giống như phần `slug` của file `categories.yml`.
	- Nội dung của file đó có phần `slug` giống tên file.

### Tạo một tag mới

1. Thêm vào `_data\tags.yml` theo quy luật
	- (1) `the`: tên của tag ở trong mỗi bài viết vẫn ghi, ví dụ `"thiết kế web"`.
	- (2) `slug`: cái dùng để tạo đường dẫn cho tag đó (`/tag/web-design`), ví dụ `web-design`.
	- (3) `name`: tên để hiển thị ở [Chủ đề](/projects)
2. Tạo một file `.html` tương ứng trong thư mục `\tag` với tên được đặt giống như cái (2). Nội dung của nó đảm bảo 
	- `title`: giống (3), có thể sửa khác.
	- `slug`: giống (1)

### Đang dùng

Các categories có sẵn
<div class="thi-columns">
<ul>
{% for cat in site.data.categories %}
<li><code class="highlighter-rouge">{{ cat.slug }}</code> : <a href="/{{cat.slug}}">{{ cat.name }}</a></li>
{% endfor %}
</ul>
</div>

Các [tags](/tags) có trong mục [Chủ đề](/projects)

<p>
{% for dtag in site.data.tags %}
<code class="highlighter-rouge">{{ dtag.the }}</code>
{% if forloop.last == false %}
, 
{% else %}
.
{% endif %}
{% endfor %}
</p>

Các [tags](/tags) đang dùng

<p>
{% for tag in site.tags %}
<code class="highlighter-rouge">{{ tag[0] }}</code>
{% if forloop.last == false %}
, 
{% else %}
.
{% endif %}
{% endfor %}
</p>