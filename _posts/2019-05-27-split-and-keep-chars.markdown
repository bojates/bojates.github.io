---
title: Split and keep chars
layout: post
---
When we split a string, we normally lose the character we split on.

e.g. 

```
str = 'My cat has a hat'
str.split => ['My', 'cat', 'has', 'a', 'hat'] (no spaces)
```

However, what if we want to keep the character we're splitting on? 

```
str = 'CrazyCats!'
str.split('C') => ["", "razy", "ats!"]
```

To add the delimeter to the end of the first string, use
```
content.split(/(?<=[C])/) => ["C", "razyC", "ats!"]
```

To add the delimiter to the front of the second string, use: 
```
content.split(/(?=[C])/) => ["Crazy", "Cats!"]
```
