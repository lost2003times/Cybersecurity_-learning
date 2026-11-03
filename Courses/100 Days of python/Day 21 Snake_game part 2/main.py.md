```
from turtle import Screen
import time
from snake import Snake
from food import Food
from score import ScoreBoard

screen = Screen()
screen.setup(width=600, height=600)
screen.bgcolor("black")
screen.title("Snake game is it!!!!")
screen.tracer(0)
screen.listen()


snake = Snake()
food = Food()
score = ScoreBoard()

screen.onkey(snake.up,"Up")
screen.onkey(snake.down,"Down")
screen.onkey(snake.left,"Left")
screen.onkey(snake.right,"Right")

game_is_on = True
while game_is_on:
    screen.update()
    time.sleep(0.1)
    snake.move()

#Detecting the food collision
    if snake.mouth.distance(food) < 15:
        food.next_food()
        score.score_update()
        snake.extend()

#Detecting collision with the wall
    if snake.mouth.xcor() > 285 or snake.mouth.xcor() <-285 or snake.mouth.ycor() >285 or snake.mouth.ycor() <-285:
        game_is_on = False
        score.game_over()

# Detecting collision with the tail
    for segment in snake.whole_snake[1:]:
        if snake.mouth.distance(segment) < 10:
            game_is_on = False
            score.game_over()
        
screen.exitonclick()
```

