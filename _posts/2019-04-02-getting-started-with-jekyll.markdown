---
title: "About this site, and getting started with Jekyll"
layout: post
date: 2019-04-02 17:11:47
categories: jekyll
tags: jekyll
---
## Background
My course at [Launch School](http://launchschool.com/) wants me to keep a blog for personal notes and also for public consumption. It recommends Medium, but my preference is to have somewhere I can collect my notes locally and then share them publicly. 

I looked at Notion, but it is so flexible I thought I would get trapped in a rabbit hole of setup everytime I went to make a note. I use Sublime Text and like the idea of a Sublime Text window that has my notes in it, for me to refer to easily. 

As a result, I am trying GitHub and Jekyll for this purpose. 

As this site is mostly for me, I don't promise to not change the url structure etc. as my needs develop. 

## Getting setup

Jeyll and GitHub pages are designed to play nicely together. What I did: 

 - Set up a repository in my GitHub account to get my user github pages working. Info at [https://pages.github.com/](https://pages.github.com/)
 - Cloned the repository to my local computer. 
 - Installed the Jekyll gem. (`gem install jekyll bundler`)
 - Ran `Jekyll new .` in the repository folder. 
 - Changed a few items in the `_config.yml`
 - Installed the SublimeText Jekyll package, to help create new entries easily
 - Added `_sites/` to `.gitignore`
 - Wrote this blog entry.
 - Pushed to GitHub (instructions below)
 - Modified the permalinks structure in `_config`

## Markdown reference

[Kramdown](https://kramdown.gettalong.org/quickref.html)

## To view the site locally, use

    bundle exec jekyll serve

Then navigate to: [http://localhost:4000](http://localhost:4000)

Restarting the server updates the homepage to show new blog entries. I think because it creates a rebuild. 

## To publish the site on GitHub, use

    git add .
    git commit -m 'add your message'
    git push 

View the pages at: [https://bojates.github.io/](https://bojates.github.io/) (it can take a few minutes to update.)

    

