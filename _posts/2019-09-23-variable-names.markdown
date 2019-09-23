---
title: Variable names
layout: post
---
Takeaway point: It's possible that not everyone who reads your variable names will know how your native language works. It's possible your variable names are adding friction to your own comprehension as well. 

Variable names are of huge interest to me. If we can name our variables correctly, and our classes and methods, then our code will read fluently. It will make intuitive sense. We can debug it, build on it, and catch logic errors. 

There is a world of difference between 

```ruby
class Anagram
  def initialize(word)
    @word = word
  end

  def match(words)
    words.select { |agagram_candidate| anagram?(@word, agagram_candidate) }
  end

  private

  def anagram?(word1, word2)
    return false if word1.downcase == word2.downcase ||
      word1.length != word2.length

    word2_letters = word2.downcase.chars

    word1.downcase.chars.each do |letter|
      idx = word2_letters.find_index(letter)
      return false unless idx
      word2_letters.delete_at(idx)
    end

    true
  end
end
```
and
```ruby
class Anagram
  def initialize(input)
    @input = input
  end

  def match(array)
    array.select { |w| anag?(@input, w) }
  end

  private

  def anag?(w1, w2)
    return false if w1.downcase == w2.downcase ||
      w1.length != w2.length

    w2_chars = w2.downcase.chars

    w1.downcase.chars.each do |letter|
      idx = w2_chars.find_index(letter)
      return false unless idx
      w2_chars.delete_at(idx)
    end

    true
  end
end

```

I try to use meaningful names as I work but it's not uncommon for me to spend as long refactoring a piece of simple code, with a view to readability and addressing the issues that are surfaced as a result of that, as I take to get the thing working in the first place. 

An element of this that I hadn't considered until recently is the readability of variable names for people who don't speak English as a first language. 

To me, `array` can easily be abbreivated to `arr`, `string` to `str`, `categories` to `cats`, and so on. But these abbreviations, which seem to add no friction for me, require an extra mental step for someone with good, but not native, English. 

Since realising this, I have started to be far more explicit with my naming. I have also noticed a clear improvement in my comprehension of my own code. It turns out there was some friction there after all. 
