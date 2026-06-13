```
import random 
import os
def draw_cards():
    cards = [11,2,3,4,5,6,7,8,9,10,10,10,10]
    card = random.choice(cards)
    return card

def calculate(cards):
    if sum(cards) == 21 and len(cards) == 2:
        return 0
    if 11 in cards and sum(cards) > 21:
        cards.append(1)
        cards.remove(11)
    return sum(cards)

def compare(user_score, computer_score):
    if user_score == computer_score:
        return "Draw!!!"
    elif computer_score == 0:
        return "Computer has won with an BlackJack!!!!"
    elif user_score == 0:
        return "You have won with an BlackJack!!!!"
    elif user_score > 21:
        return "You went over 21 you lose!!!"
    elif computer_score > 21:
        return "Computer went over 21, You Won"
    elif user_score >computer_score:
        return "You Win!!!"
    else:
        return "You lose."

def playgame():    
    game_over = False 
    computer_score = -1
    user_score = -1
    user_cards = []

    computer_cards = []

    for _ in range(2):
        user_cards.append(draw_cards())
        computer_cards.append(draw_cards())
    while not game_over:
        user_score = calculate(user_cards)
        computer_score = calculate(computer_cards)
        print(f"Your cards are {user_cards} and your current score is {user_score}")
        print(f"Computers first card are {computer_cards[0]}")

        if computer_score == 0 or user_score == 0 or user_score > 21:
            game_over = True
        else: 
            user_should_deal = input("Enter 'y' if you want another card or 'n' if you are scared.\n").lower()
            if user_should_deal == "y":
                user_cards.append(draw_cards())
            elif user_should_deal == "n":
                game_over = True

    while computer_score != 0 and computer_score < 17:
        computer_cards.append(draw_cards())
        #print(f"Computers second hand : {computer_cards}")
        computer_score = calculate(computer_cards)
        

    print(f"your final hand : {user_cards}, final score: {user_score}")
    print(f"Computer's final hand: {computer_cards}, computers final score: {computer_score}")
    print(compare(user_score, computer_score))

while input("Do you want to play ? 'y' or 'n' ").lower() == "y":
    os.system('cls' if os.name == 'nt' else clear)
    playgame()
```