+++
tags = ["cms", "wordpress", "hugo", "static-site"]
featured = false
description = "Read why I've moved from Wordpress CMS to Hugo static site generator"
date = "2017-08-02T19:45:00"
share = true
image = "images/post/hugo.png"
title = "Moving from Wordpress to Hugo"
slug = "moving-wordpress-hugo"
author = "Curtis Timson"
draft = false
menu = ""
comments = true
postid = 7
+++

For the past few years I've been using [Wordpress](http://www.wordpress.com) to power this blog site and have recently switched to using [Hugo](https://gohugo.io/), a static site generator. Now I'd like to share my reasons for doing this, and how you can too.

## What is Hugo?

![Hugo](/images/post/hugo.png)

[Hugo](https://gohugo.io/) is a static site generator written in Go which converts partial HTML files and Markdown files into a flattened HTML pack which can then be deployed to a web server.

Therefore there is no need for any database back-end or server-side logic.

## Advantages

### Performance

#1 advantage has to be the performance aspect. As there is no back-end logic processing and rendering HTML, the application will be served to the client much faster.

### Cheaper Web Hosting

Once again as there is no back-end to interface with, web hosting costs are reduced as only flat static files are required to power the application.

In fact this blog site is hosted by [GitHub Pages](https://pages.github.com/) and is therefore completely free.

### Offline editing

Blog articles are simple markdown files and can therefore be edited and saved offline. With Wordpress you must have an internet connection to be able to write the draft back to the MySQL database.

### Security

With CMS's such as Wordpress your application is vulnerable to database hacking in order to inject post contents with spam links and scripts.

However with a static site this security risk is far reduced by removing the database altogether.

[![Little Bobby Tables](/images/post/little-bobby-tables.png)](https://xkcd.com/327/)

### Control

Using Wordpress it can be very difficult to control the final outputted HTML of your application. Quite often you rely on plugins to provide additional functionality, but these can come at a cost of sluggish performance.

With Hugo you have full control over the HTML which is produced, and it's very easy to customise.

### Collaboration

Like with any code commits on GitHub, blog articles could be easily peer reviewed through [Pull Requests](https://help.github.com/articles/about-pull-requests/) from branches.

Furthermore if the code is kept in a public repository ([such as this one](https://github.com/curtistimson/curtis-timson)) then anyone can fork and create a code fix or post typo fix and submit it as a Pull Request.

## Disadvantages

### No Admin Interface

One of the main disadvantages of Hugo as a CMS is that there is no admin interface available for the end-user. This is fine if the application's content is managed by a developer, but otherwise this won't be so intuitive.

At very least the end-user would need to learn basic Markdown skills, or use a Markdown WYSIWYG, and then be dependant on a developer deploying their content.

### No User Comment System

As the application has no database it's not possible for the user to submit a comment to an article.

However there is a simple workaround for this by using third-party solutions. For example this blog site is using [Disqus](https://disqus.com/). In fact as Disqus has it's own comment approval system, you will receive far less spam.


## Setting up Hugo

The Hugo website has a very good Quick Start guide which will help you get setup:

https://gohugo.io/getting-started/quick-start/

Generally this involves:

 - Installing Hugo locally
 - Creating a new Hugo site
 - Adding a theme
 - Adding content

### Themes

As the Hugo website states there are a lot of prebuilt Hugo themes available and I highly recommend installing one of these initially if only for a working example of the Hugo syntax and folder structure.

For example this blog site is built on the [Bleak](https://themes.gohugo.io/bleak/) theme.

Themes will be stored in the following folder structure:

```markup
|--themes
   |--theme-name
      |--layouts
         |--partials
         |--index.html
```

If for example you wished to modify the content of the `index.html` you can simply edit the theme, however this would be overwritten next time you updated the theme.

However any file which exists in the root `layouts` folder will overwrite the theme. Therefore you can place your customised version in the following folder structure:

```markup
|--layouts
   |--index.html //custom file
|--themes
   |--theme-name
      |--layouts
         |--partials
         |--index.html
```


## Migrating from Wordpress

### Wordpress to Markdown conversion

There are various Wordpress plugins available to help you migrate your posts over to Hugo such as:

https://github.com/SchumacherFM/wordpress-to-hugo-exporter

Personally as I didn't have a great deal of posts on Wordpress I migrated these manually and used it as a opportunity to tidy up old content.

### Migrating comments to Disqus
There is a Wordpress plugin available to help migrate your Wordpress comments over to Disqus here:

https://wordpress.org/plugins/disqus-comment-system/

### URL Aliasing
When migrating from Wordpress I found that I required slightly different URLs for my blog posts. So that I wouldn't lose the link equity from existing sources I added aliases to the front-matter in the Hugo posts. This can be done like so:

```js
+++
title = "Check javascript function exists before calling it"
aliases = [
    "/js/check-javascript-function-exists-before-calling-it/"
]
+++
```

## Summary

I highly recommend migrating to a static-site generator for any developer maintaining a blog.

However Hugo isn't the only choice. In fact [StaticGen.com](https://www.staticgen.com/) currently list over 150 different alternatives.

If you have anything you'd like to add please comment below (or create a pull request!)

## Further Reading

- [Smashing Magazine - Why Static Site Generators Are The Next Big Thing](https://www.smashingmagazine.com/2015/11/modern-static-website-generators-next-big-thing/)
- [DWB - An Introduction to Static Site Generators ](https://davidwalsh.name/introduction-static-site-generators)
- [Hugo vs. Jekyll: Comparing the leading static website generators](https://opensource.com/article/17/5/hugo-vs-jekyll)
- [Philipp Hauer - Moving from Wordpress to Hugo](https://blog.philipphauer.de/moving-wordpress-hugo/)
