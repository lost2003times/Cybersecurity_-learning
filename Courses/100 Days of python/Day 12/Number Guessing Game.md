```
import random

def guess_it():
    
    def game():
        game_level = input("Choose your level : Easy or Hard \n").lower()
        if game_level == "easy":
            lives = 10
        elif game_level == "hard":
            lives = 5

        while lives > 0:
            choose = int(input("Enter your guess: "))
            if choose < guess_num:
                print("Too low.")
                lives -= 1
                print("Your lives: ", lives)
            elif choose > guess_num:
                    print("Too High.")
                    lives -= 1
                    print("Your lives: ",lives)
            else:
                    print("You Won.")
                    break
        if lives == 0:
                 print("You lost!!!")
                 print(f"The number was {guess_num}.")
    guess_num = random.randint(1,100)
    print(guess_num)
    print("Welcome to the guessing game.\n")

    
    game()
guess_it()
```