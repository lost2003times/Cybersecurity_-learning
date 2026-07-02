```
from data import data
import random


def format_data(option):
    option_name = option["name"]
    option_desc = option["description"]
    option_country = option ["country"]
    return f"{option_name}, a {option_desc} and from {option_country}"

def check_answer(user_guess, a_followers, b_followers):
    if a_followers > b_followers:
        return user_guess == 'a'
    else:
        return user_guess == 'b'
score = 0
option_b = random.choice(data)
should_continue = True
while should_continue:
    option_a = option_b
    option_b = random.choice(data)

    if option_a == option_b:
        option_b = random.choice(data)
    print(f"Compare A : {format_data(option_a)}")
    print(f"Compare B : {format_data(option_b)}")

    guess = input("Who has more followers A or B? ").lower()
    print ("\n "* 20)
    a_followers_count = option_a["follower_count"]
    b_followers_count = option_b["follower_count"]
    is_correct = check_answer(guess, a_followers_count, b_followers_count)

    if is_correct :
        score += 1
        print(f"You are right, current score is {score}")
    else:
        print(f"You are wrong. Your final score is {score}")
        should_continue = False

```