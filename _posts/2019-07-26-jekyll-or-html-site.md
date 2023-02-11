---
layout: post
title: "Choosing between Jekyll or a HTML & CSS site?"
excerpt_seperator: "<!--more-->"
categories:
  - technology
tags:
  - html
  - jekyll
  - web design
---

Choosing between a Jekyll or HTML & CSS site is simple. But, it can become difficult when you are unsure about your needs.

<!--more-->

### Factors to consider before choosing from between these two are:
- **Do you need a blog along with your site?**
  <br>- If you need a blog to keep with your site, Jekyll makes it easier to maintain the code with the `_includes` and `_layouts`. You can blog locally in your favorite editor and then push the changes to your hosting ( just upload the updated files in `_site` folder ) or GitHub Pages. Hosting on GitHub Pages provides you with a virtual CMS. Any changes made in Markdown, HTML and Yaml files will update automatically on your site ).

- **Do you need to update your site regularly?**
  <br>- If your site rarely needs to upgrade and you have some knowledge of HTML & CSS then it is better to use HTML. Otherwise, use Jekyll to build your site.<br>Jekyll makes it easier for the site administrators to review the code as it is modular, with no need to repeat the code for a common component like navigation or footer. Any changes made to the code for the navigation in the includes folder will reflect sitewide. You can separate your website layout into many types usually default, pages and posts. Each layout can be designed as per the need.

- **Is your site extremely simple with few pages?**
  <br>- If your site is extremely simple with just few pages, a simple HTML & CSS site should be the option to choose.


This article first appeared on as a blog post for [Jekyll-Vfolio](https://github.com/ravigupta-art/jekyll-vfolio) theme.
