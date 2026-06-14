## Deck of cards

There are many card games that you could implement in Python: poker, war, blackjack... Naturally, implementing an entire card game is a long and complicated process. In this exercise, we're only going to focus on a tiny part that could be used in many card games: implementing a deck of cards using OOP with some basic, ready-to-use operations.

Your task is to implement two classes: **Card** and **Deck**. The Deck should be a standard 52-card deck as described here: [wiki page](https://en.wikipedia.org/wiki/Standard_52-card_deck).

The **Card** should be a very simple class with just two attributes: **suit** and **value**. It should also have a method named `present()` that returns a string showing `{value} of {suit}`. For instance, for a card created in the following way `Card('hearts', '10')` the method should return `10 of hearts`.

The **Deck** should have one attribute: **cards**. It should be a list of Card objects representing a full card deck with all combinations of suits and values. For your convenience, here are the exact values that should be used:

```python
suits = ['hearts', 'diamonds', 'clubs', 'spades']
values = ['Ace', '2', '3', '4', '5', '6', '7', '8', '9', '10', 'Jack', 'Queen', 'King']
```

In other words, the Deck should internally have a **cards** list with card objects such as `Card('hearts', 'Ace')` or `Card('spades', '5')`. When created, each object of the Deck class should have exactly 52 cards, one of each value and suit.

The Deck class should also make available the following methods:

1. `shuffle()`: this method should randomly change the order of cards in the deck*.
2. `deal()`: this method should return one **card object** from the Deck (the currently last card in the `cards` list) and then also remove that object from the Deck. If there are no cards left, return **None**.
3. `count_remaining()`: this method should return the number of cards (**an integer**) in the deck
4. `get_remaining()`: this method should return **a list of strings**, each string describing a single remaining card, using the present() method for the Card class described above. For instance, if there are two cards remaining in the deck, the returned list could look as follows (the remaining cards shown below are picked at random):

   ```python
   ['3 of hearts', 'Jack of spades']
   ```

* You can use the shuffle method from the random module like this: `random.shuffle(list_name)`

<details>
<summary>Initial Script</summary>

```python
class Deck:
    pass

class Card:
    pass
```
</details>
<hr>

<details>
<summary>Solution</summary>

```python
import random

class Deck:
    def __init__(self):
        suits = ['hearts', 'diamonds', 'clubs', 'spades']
        values = ['Ace', '2', '3', '4', '5', '6', '7', '8', '9', '10', 'Jack', 'Queen', 'King']
        
        # Initialize the 52-card deck using nested loops
        self.cards = [Card(suit, value) for suit in suits for value in values]
    
    def shuffle(self):
        random.shuffle(self.cards)

    def deal(self):
        if len(self.cards) > 0:
            return self.cards.pop()
        return None

    def count_remaining(self):
        return len(self.cards)

    def get_remaining(self):
        return [card.present() for card in self.cards]

class Card:
    def __init__(self, suit, value):
        self.suit = suit
        self.value = value

    def present(self):
        return f"{self.value} of {self.suit}"
```
</details>
