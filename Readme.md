# Intro
[This](yuvaldv.github.io) personal website & portfolio was built using [Hugo](https://gohugo.io) and deployed to [GitHub Pages](https://pages.github.com/).

# Hugo Installation
## MacOS
Install [brew](https://brew.sh/)
		brew install hugo

## [Windows](https://gohugo.io/tutorials/installing-on-windows/)

# Initialization
First We'll Create 2 new [GitHub](github.com) repo's `username.github.io`[^Which will contain our final html files. Notice:repo name must match your username and GitHub url exactly or the site won't go live.] & `mySite-hugo`[^which will contain our source code]

Now we'll create the website on our local machine, and sync it with both repo's using [submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules).
```
		$ hugo new site <project>
		$ cd <project>
		$ git init
		$ git remote add origin  https://github.com/username/mySite-Hugo.git
		$ git submodule add https://github.com/username/username.github.io.git public
		$ hugo
		$ git add *
		$ git commit -m 'initialization'
		$ git push origin master
		$ cd public
		$ git add *
		$ git commit -m 'initialization'
		$ git push origin master
```

# Website Customization & update
Here are some [themes](https://themes.gohugo.io/) to get you started,
i'll be using `https://github.com/kishaningithub/hugo-creative-portfolio-theme.git` a.k.a Creative Portfolio

in the terminal, from `/<project>/`
	$ cd themes
	$ git clone https://github.com/kishaningithub/hugo-creative-portfolio-theme.git

in the file browser
- Copy & *edit* `config.toml` from `<project>/themes/<theme>/example-site` to `<project>`
- Copy archetypes from `<project>/themes/<theme>/archetypes` to `<project>/archetypes`

in the terminal, from `/<project>/`
```
	$ hugo
	$ git add *
	$ git commit -m 'customization'
	$ git push origin master
	$ cd public
	$ git add *
	$ git commit -m 'customization'
	$ git push origin master
```
As you can see, we're pushing twice, to 2 different repo's.

# Local server

in the terminal from `/<project>/`
```
	$ hugo server
```
if you want to check it on your mobile though your local network
```
	$ hugo server -D --bind <yourIP> --baseURL http://<yourIP>
```
replace `<yourIP>` with your local ip e.g.
```
$ hugo server -D --bind 192.168.1.3 --baseURL http://192.168.1.3
```
then visit `http://192.168.1.3:1313`

if it's in a specfic subdomain like `portfolio` for instance
```
$ hugo server -D --bind 192.168.1.3 --baseURL http://192.168.1.3/portfolio
```
then visit `http://192.168.1.3:1313/portfolio`
# Posting new content
From `/<project>/`
		hugo new post/welcome.md
		hugo new page/about.md
		hugo new category/post.md

Edit these files in your fav text/markdown editor

and push to github, in the terminal, from `/<project>/`
```
	$ hugo
	$ git add *
	$ git commit -m 'customization'
	$ git push origin master
	$ cd public
	$ git add *
	$ git commit -m 'customization'
	$ git push origin master
```

# Multiple websites/themes

# Mutli-language
