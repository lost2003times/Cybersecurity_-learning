```
from hangman_wordlists import wordlist
import random

lives = 6
choose_word = random.choice(wordlist)
print(choose_word)

place_holder = ""
wordlength = len(choose_word)
for position in range(wordlength):
        place_holder += "_"
print(place_holder)

correct_letters = []
Game_over = False
while not Game_over:
    
    guess = input("Choose a letter: ").lower()
    print(guess)
    display = ""

    for letter in choose_word:
        if letter == guess:
            display += letter
            correct_letters.append(guess)
            print("Lives left", lives,"/6")
        elif letter in correct_letters:
             display += letter 
        else: 
            display += "_"
            
    if guess not in choose_word:
         lives -= 1
         print("Lives left", lives,"/6")
         if lives == 0:
              print("YOu lose, The word was ", choose_word)
              Game_over = True
    print(display)

    if "_" not in display:
         print("YOu win.")
         Game_over = True
```