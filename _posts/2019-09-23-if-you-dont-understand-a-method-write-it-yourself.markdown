---
title: If you don't understand a method, write it yourself
layout: post
---

"If you don't understand a method, write it yourself." I heard this tip the other day and it slightly blew my mind. So obvious, and so useful. 

Here's an example of me giving this a go. 

A method that I love in ruby, but often forget to use, is `String#scan`. My version is: 

```
def scan(string, regexp)
  results = []

  while string =~ regexp
    matches = string.match(regexp)

    if matches.size == 1
      results << matches[0]
    else
      results << matches[1..matches.size - 1]
    end

    string = string.sub(matches[0], '')
  end

  results
end
```

My implementation takes a string and regexp as arguements. It initializes a results variable and points it to an empty array. It then checks to see if the string has any matches against the regexp. If it does, it grabs the matches. If there is just one match, that gets added to the array. If there is more than one match result this indicates the regexp is getting the result in parts. We add those parts to our result array. 

We then remove the match from the string, and look again to see if there is another match. 

Finally, we return the results array. 

As I wrote it, I ran tests to check it would behave the same as `String#scan`. 

I used regexps that are used in the `String#scan` documentation. 

```ruby
require 'minitest/autorun'

class TestScan < Minitest::Test
  def setup
    @text = 'This is my very long test'
  end

  def test_splits_same_as_scan_1
    regexp = /.../
    assert_equal(@text.scan(regexp), scan(@text, regexp))
    assert_equal(@text.scan(regexp), scan(@text, regexp))
  end

  def test_splits_same_as_scan_2
    regexp = [/.../, /\w+/, /(...)/]
    regexp = /\w+/
    assert_equal(@text.scan(regexp), scan(@text, regexp))
  end

  def test_splits_same_as_scan_3
    regexp = /(...)/
    assert_equal(@text.scan(regexp), scan(@text, regexp))
  end

  def test_splits_same_as_scan_4
    regexp = /(..)(..)/
    assert_equal(@text.scan(regexp), scan(@text, regexp))
  end

  def test_splits_same_as_scan_4
    regexp = /(..)(..)(.)/
    assert_equal(@text.scan(regexp), scan(@text, regexp))
  end

  def test_splits_same_as_scan_nomatch
    regexp = /jemima/
    assert_equal(@text.scan(regexp), scan(@text, regexp))
  end

  def test_splits_same_as_scan_single_letter
    regexp = /t/
    assert_equal(@text.scan(regexp), scan(@text, regexp))
  end
end
```
