---
title: Shuffle method
layout: post
categories: ruby
---
for the game of 21, I coded the following methods: 

```ruby
def build_deck
    deck = []
    SUITS.each do |s|
        CARD_VALUES.each do |c|
            deck << "#{c} of #{s}"
        end
    end
    deck
end

def get_card(deck)
    card = deck.sample
    deck.delete(card)
    card
end
```
A far easier approach: 

```ruby
def build_deck
deck = []
    SUITS.each do |s|
        CARD_VALUES.each do |c|
            deck << "#{c} of #{s}"
        end
    end
    deck.shuffle
end

def get_card(deck)
    deck.pop
end
```
