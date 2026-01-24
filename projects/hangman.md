---
layout: project
type: project
image: img/pythonsym.png
title: "Hangman Game"
date: 2024
published: true
labels:
  - Python
  - Beginner Project
  - Game
summary: "This is a program I made back in 2024 that simulates a game of Hangman"
---

<div class="text-center p-4">
  <img width="600px" src="../img/hangmanout.png" class="img-thumbnail" >
</div>

This project the first one I made outside of school reasons and represents an important step in trying to apply programming skills independently. It is a Python-based command-line implementation of the classic Hangman game, where a random word is selected from a predefined list and the user guesses letters one at a time. The program updates the displayed word as correct guesses are made and tracks incorrect guesses by limiting the number of remaining attempts, providing clear feedback after each turn.

Working on this project helped reinforce core programming concepts such as loops, conditional logic, lists, and user input handling. It also strengthened my problem-solving skills by requiring me to think through game flow, edge cases, and user interaction without structured teaching guidance. This project reflects my growth from when I started with Python and my ability to build interactive programs more independently.

**Code Sample:**

```cpp
import random

word_bank = ["council", "insurance", "spot", "keep", "fascinate", "treatment", "policy", "decisive",
             "dialect", "pat", "fast", "disaster", "rainbow", "siege"] # change to your own words

word = random.choice(word_bank)

display = []
for letter in word:
    display.append("_")

guessed_letters = []
lives = 6

print("Hangman Game")
print(" ".join(display))

while lives > 0 and "_" in display:
    guess = input("Guess a letter: ").lower()

    if len(guess) != 1:
        print("Only one letter.")
        print()
        continue

    if guess in guessed_letters:
        print("Guessed that letter already.")
        print()
        continue

    guessed_letters.append(guess)

    if guess in word:
        print()
        print("Correct guess!")
        for i in range(len(word)):
            if word[i] == guess:
                display[i] = guess
    else:
        lives -= 1
        print()
        print("Wrong guess.")
        print("Lives left:", lives)

    print(" ".join(display))
    print("Guessed letters:", guessed_letters)

if "_" not in display:
    print()
    print("You win! The word was:", word)
else:
    print()
    print("Game over. The word was:", word)
```
