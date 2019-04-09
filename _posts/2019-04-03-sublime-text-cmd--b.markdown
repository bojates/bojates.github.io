---
title: "Sublime Text ⌘b and other tips for Launch School exercises"
layout: post
categories: sublime_text ruby
---

Holy smokes. 

In Sublime Text, type `⌘b` and it will run the code in a terminal window right before your eyes. 

Let's just say I wish I'd known that before 130 ruby excercise :-) 

Another thing I wish I'd known: to create a file for each exercise, you can do this at command line: 

    for i in {01..10}; do touch ${i}.rb; done

Or the Ruby CLI version:

    ruby -e '(1..10).each { |i| File.open("#{"%02d" % i}.rb", "w") {} }'
