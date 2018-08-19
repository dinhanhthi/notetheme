---
title: How to install NoteTheme
categories: notetheme
tags: [notetheme, jekyll, theme]
maths: 1
comment: 1
---

In this tutorial, I suppose that you are new to [Github Pages](https://pages.github.com/) and [Jekyll](https://jekyllrb.com/), just follow the ones you need and don't forget to leave a comment below.

{% include tip.html content="I'm not a native English speaker, please ignore my bad expressions." %}

{% include toc.html %}

## How to create a Github Page?

In the case you don't have any Github Page, follow following rules, otherwise please step to next steps. **For Vietnameses**, please read [this article](https://toituhoc.xyz/huong-dan-nhanh-tao-trang-web-github-page-dung-theme-co-san).
1. [Create](https://github.com/join?source=header-home) a Github account, don't forget to verify your email before loging in. I suppose that you signed up with name `dinhanhthi`.
2. Login to your Github account.
3. Create a new repository by clicking **New** on the right side of *Repositories* section and naming your repo with `<your-account>.github.io`. For example, my Github account is "*dinhanhthi*", so I name this repo "*dinhanhthi.github.io*". We need to name the repo like this because your website will have an address like **https://\<your-account\>.github.io**.
4. Basically, you now have a place where you can put your website, you can choose either a built-in theme from Github or an external theme. 
	- If you wanna apply **[NoteTheme](https://github.com/dinhanhthi/NoteTheme)** (or [other external theme](http://jekyllthemes.org/)), please step to next section ([How to apply NoteTheme](#how-to-apply-notetheme)) and ignore following steps in this section.
	- If you wanna create immediately a buit-in theme from Github, please continue to step 5.
5. On your repo on github, click on tab **Settings**, on the left hand side, choose tab **Options** (default) and then go to section **Github Pages**, click on **Choose a theme**.
6. Choose a theme you like and then click on **Select theme**
7. A new page appears, write something on **Commit changes** and then click on **Commit changes**.
8. Done, now you have a page, check it out at **https://\<your-account\>.github.io**

{% include tip.html content="Don't worry if you followed step 5-8 and you wanna apply other themes, just keep going to next section." %}



## How to apply NoteTheme?

1. Download and install **[Github Client](https://desktop.github.com/)** (GC). GC helps you "upload" changes from local host (on your own computer) to your remote (on Github server).
2. Login to GC with the account created in step 1.
3. Clone the repo created in step 3 of previous section to your local computer:
	1. Come back to the repo's directory, click on **Set up in Desktop**, a popup appears to ask you "*Open Github Desktop?*", choose **Open Github Desktop**
	2. This will open GC on your computer, click on button **Clone**
	3. Choose the location where you save your repo on your computer. A folder whose name is **\<your-account\>.github.io** will be created.
4. From this step, you will apply a theme [downloaded from the internet](http://jekyllthemes.org) for your Github page. In this case, you will apply **[NoteTheme](https://github.com/dinhanhthi/NoteTheme)**.
5. Download [NoteTheme](https://github.com/dinhanhthi/NoteTheme) to your local computer (a file .zip)
6. Delete all files and folders in folder **\<your-account\>.github.io** created in step 3.3.
7. Extract all files and folders from file .zip in step 5 to folder **\<your-account\>.github.io**
8. Open file **_config.yml** and change some fields in this file
	1. `title`: your website's name
	2. `description`: your website's description
	3. `baseurl`: leave blank (i.e., `""`)
	4. `url`: `<your-account>.github.io`
	5. `paginate`: number of posts on each page (default is 28)
	6. `banner`: directory to your website's banner
	7. `favicon`: directory to your website's favicon (icon appears on the left on browser's tab)
	8. `user`: change all your personal information (`name`, `email`, `website`, `avatar`,...)
	9. Save and close **_config.yml**
9. Open Github Desktop to see the changes
	1. Write something on field commit
	2. Click on **Commit to master** and then **Publish branch**
10. All done! Go to **https://\<your-account\>.github.io** to see the changes, you may wait a little minutes to get the changes.


## Get some errors?

- If you have some unexpected errors, please tell me on the comment section below.
- If you wanna config more on this theme, please read [How to use NoteTheme]({{ site.baseurl }}/how-to-use-notetheme).
- If you find something wrong on this post, please tell me to fix them. 

Thank you and good luck.