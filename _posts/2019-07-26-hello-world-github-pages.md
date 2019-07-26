---
layout: post
title: "Hosting a simple Hello World site using Github Pages"
excerpt_seperator: "<!--more-->"
categories:
  - technology
tags:
  - html
  - github
---
This is a tutorial for hosting a Hello World site using gh-pages. This will help you understand the basics of GitHub Pages and use these basics to host a full-fledged site using gh-pages.

<!--more-->

## 1. Create a repository   

  For this, you need to initially have a GitHub account. Sign up your account using [this link](https://github.com/)   
  In the upper-right corner of any page, click '+', and then click **New repository**.

  ![Clicking on New Repository]({{ site.baseurl }}/images/HelloWorld_Tutorial/creating_repo1.png){: .align-center}

  ![Creating a new repository]({{ site.baseurl }}/images/HelloWorld_Tutorial/creating_repo2.png){: .align-center}   

  Click on **Create Repository**.  

## 2. Creating a simple Hello World html file

  In the code section, you will see **Quick Setup**. Click on **creating a new file**.   

  ![Creating a new file]({{ site.baseurl }}/images/HelloWorld_Tutorial/creating_newfile.png){: .align-center}

  Add file name as *index.html* and type in a simple Hello World html program.

  ![Creating index.html]({{ site.baseurl }}/images/HelloWorld_Tutorial/creating_index.png){: .align-center}

## 3. Commit new file

  In GitHub, to save a file or its changes we need to commit changes.   
  To commit, scroll down and in *Commit new file* section write up the changes or the message you might help you get to it later easily.Finally, click on **Commit new file**.

  ![Commiting a new file]({{ site.baseurl }}/images/HelloWorld_Tutorial/commiting_indexfile.png){: .align-center}

## 4. Create *gh-pages* branch

  To use Github Pages,we need to create a new branch as **gh-pages**.   
  For this, click on *Branch:master* and type in *gh-pages*. In the dropdown option, click on *Create branch:gh-pages*.   
  If we initially had *gh-pages* branch then it will switch with the *master* branch. but since we do not have that branch it creates it.

  ![Creating gh-pages branch]({{ site.baseurl }}/images/HelloWorld_Tutorial/creating_ghpagesbranch.png){: .align-center}

## 5. And testing out

  In your browser, type in `https://username.github.io/Hello-World` where username is your current Github username.

  Finally, you can check up Hello World displayed on your browser. The ouput will be as shown in the following image:

  ![Hello World hosted]({{ site.baseurl }}/images/HelloWorld_Tutorial/helloworld_hosted.png){: .align-center}

This article first appeared on as blog post for [Jekyll-Vfolio](https://github.com/ravigupta-art/jekyll-vfolio) theme.
