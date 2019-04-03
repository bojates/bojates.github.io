---
title: "Getting started with Jekyll"
layout: post
date: 2019-04-02 17:11:47
categories: jekyll update
---
Jeyll and GitHub pages are designed to play nicely together. What I did: 

 - Set up a repository in my GitHub account to get my user github pages working. Info at [https://pages.github.com/](https://pages.github.com/)
 - Cloned the repository to my local computer. 
 - Installed the Jekyll gem. (`gem install jekyll bundler`)
 - Ran `Jekyll new .` in the repository folder. 
 - Changed a few items in the `_config.yml`
 - Installed the SublimeText Jekyll package, to help create new entries easily
 - Added `_sites/` to `.gitignore`
 - Wrote this blog entry.

## Markdown reference

[Kramdown](https://kramdown.gettalong.org/quickref.html)

## To view the site locally, use

    bundle exec jekyll serve

Then navigate to: [http://localhost:4000](http://localhost:4000)

Restarting the server updates the homepage to show new blog entries. I think because it creates a rebuild. 

## To publish the site on GitHub, use

    git add .
    git commit -m 'add your message'
    git push origin master

View the pages at: [https://bojates.github.io/](https://bojates.github.io/)

    

