```
from turtle import Turtle, Screen, clear
import random

is_race_on = False
screen = Screen()
screen.setup(width=500, height=400)
user_guess = screen.textinput(title="Make a guess", prompt="Choose your favorite color: ")
colors = ["red", "blue", "green", "yellow", "purple", "orange"]
y_positions = [0,50,100,-50,-100,-150]
all_turtles = []

for turtle_race in range(0,6):
    jim = Turtle(shape="turtle")
    jim.penup()
    jim.color(colors[turtle_race])
    jim.goto(x=-240, y=y_positions[turtle_race])
    all_turtles.append(jim)

if user_guess:
    is_race_on = True

while is_race_on:
    for turtle in all_turtles:
        if turtle.xcor() > 220:
            is_race_on = False
            winning_color = turtle.pencolor()
            if winning_color == user_guess:
                print(f"You've won! The {winning_color} turtle is the winner!")
            else:
                print(f"You've lost! The {winning_color} turtle is the winner!")
        random_distance = random.randint(0,10)
        turtle.forward(random_distance)

screen.exitonclick()
```

