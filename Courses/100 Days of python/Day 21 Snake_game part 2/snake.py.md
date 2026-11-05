 ```
from turtle import Turtle

X_POS = [0,-20,-40]
MOVE_DIS = 20
class Snake:

    def __init__(self):
        self.whole_snake = []
        self.create_snake()
        self.mouth = self.whole_snake[0]

    def create_snake(self):
        for i in range(0,3):
            self.increase((X_POS[i], 0))
            
    def increase(self,position):
        tim = Turtle()
        tim.shape("square")
        tim.color("white")
        tim.penup()
        tim.goto(position)
        self.whole_snake.append(tim)

    def extend(self):
        self.increase(self.whole_snake[-1].position())

    def move(self):
        for seg_num in range(len(self.whole_snake) -1,0,-1):
            new_x = self.whole_snake[seg_num -1].xcor()
            new_y = self.whole_snake[seg_num -1].ycor()
            self.whole_snake[seg_num].goto(new_x,new_y)
        self.whole_snake[0].forward(MOVE_DIS)

    def up(self):
        if self.whole_snake[0].heading() != 270:
            self.whole_snake[0].setheading(90)

    def down(self):
        if self.whole_snake[0].heading()!= 90:
            self.whole_snake[0].setheading(270)

    def left(self):
        if self.whole_snake[0].heading()!=0:
            self.whole_snake[0].setheading(180)

    def right(self):
        if self.whole_snake[0].heading()!=180:
            self.whole_snake[0].setheading(0)
```