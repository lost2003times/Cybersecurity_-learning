```
from turtle import Turtle, Screen, colormode, circle
import random


jim = Turtle()

jim.speed("fastest") 

colormode(255) 

def random_color():
    r = random.randint(0, 255)
    g = random.randint(0, 255)
    b = random.randint(0, 255)
    return (r, g, b)

for _ in range(0,120):
    jim.color(random_color())
    jim.circle(100)
    jim.right(3)

screen = Screen()
screen.exitonclick()
```
