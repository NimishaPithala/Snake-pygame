# Snake-pygame
snake game using python
pip install turtles
pip install random
import turtle
import random
import time
# creating screen for the game
screen = turtle.Screen()
screen.title('SNAKE GAME')
screen.setup(width = 1000, height = 800)
screen.tracer(0)
turtle.bgcolor('orange')
turtle.speed(3)
turtle.pensize(4)
turtle.penup()
turtle.goto(-290,200)
turtle.pendown()
turtle.color('black')
turtle.forward(500)
turtle.right(90)
turtle.forward(500)
turtle.right(90)
turtle.forward(600)
turtle.right(90)
turtle.forward(500)
turtle.penup()
# creating a snake
snake=turtle.Turtle()
snake.speed(0)
snake.shape('circle')
snake.color("black")
snake.penup()
snake.goto(0,0)
snake.direction='stop'
food=turtle.Turtle()
food.speed(0)
food.shape('square')
food.color('red')
food.penup()
food.goto(20,20)
used_food=[]
scoring=turtle.Turtle()
scoring.speed(0)
scoring.color("black")
scoring.penup()
scoring.hideturtle()
scoring.goto(0,300)
scoring.write("Score: ",align="center",font=("Courier",24,"bold"))
#keyboard settings
def snake_go_up():
if snake.direction !="down":
snake.direction="up"
def snake_go_down():
if snake.direction !="up":
snake.direction="down"
def snake_go_left():
if snake.direction !="right":
snake.direction="left"
def snake_go_right():
if snake.direction !="left":
snake.direction="right"
def snake_go():
if snake.direction=="up":
y=snake.ycor()
snake.sety(y+10)
if snake.direction=="down":
y=snake.ycor()
snake.sety(y-10)
if snake.direction=="left":
x=snake.xcor()
snake.setx(x-10)
if snake.direction=="right":
x=snake.xcor()
snake.setx(x+10)
screen.listen()
screen.onkeypress(snake_go_up,"up")
screen.onkeypress(snake_go_down, "down")
screen.onkeypress(snake_go_left, "left")
screen.onkeypress(snake_go_right, "right")
# snake and food win situtation
if snake.distance(food)< 10:
x = random.randint(-290,270)
y = random.randint(-240,240)
fruit.goto(x,y) 
scoring.clear()
score+=1
scoring.write("Score:{}".format(score),align="center",font=("Courier",28,"bold"))
delay-=0.001               
new_food = turtle.Turtle()
new_food .speed(0)
new_food .shape('square')
new_food .color('red')
new_food .penup()
old_food.append(new_food )
for index in range(len(old_food)-1,0,-1):
a = old_food[index-1].xcor()
b = old_food[index-1].ycor()
old_food[index].goto(a,b)                        
if len(old_food)>0:
a= snake.xcor()
b = snake.ycor()
old_food[0].goto(a,b)
snake_go()
# snake and border lost situation
if snake.xcor()>280 or snake.xcor()< -300 or snake.ycor()>240 or snake.ycor()<-240:
time.sleep(1)
screen.clear()
screen.bgcolor('blue')
scoring.goto(0,0)
scoring.write(" GAME OVER \n Your Score is {}".format(score),align="center",font
("Courier",20,"bold"))
#snake and its body lost situation
for food in old_food:
if food.distance(snake) < 10:
time.sleep(1)
screen.clear()
screen.bgcolor('blue')
scoring.goto(0,0)
scoring.write("GAME OVER \n Your Score is {}".format(score),align="center",font=("Courier",28,"bold"))
                
