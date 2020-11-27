# clock-using-python



import turtle
import time

t = turtle.Turtle()
x = 0
y = 0
t.home()
t.speed(0)
y = -100
t.penup()
t.goto(x,y)
t.pendown()
t.circle(100)
t.penup()
t.home()
y = -60
t.goto(x,y)
t.pendown()
t.begin_fill()
t.fillcolor("green")
t.circle(60)
t.end_fill()
t.penup()
t.home()
t.left(90)
for i in range(12):
    t.right(360/12)
    t.forward(85)
    t.write(i+1)
    t.goto(0,0)

def _draw_hour_arm():
    t.penup()
    t.home()
    t.right(180)
    t.pendown()
    t.pensize(5)
    t.forward(40)



def _draw_minute_arm():
    t.penup()
    t.home()
    t.right(270)
    t.pendown()
    t.pensize(3)
    t.forward(70)

_draw_hour_arm()
_draw_minute_arm()
t.pensize(2)
angle = 0

while True:
    start = time.time()
    first_start = 1
    if first_start == 1:
        t.penup()
        t.home()
        t.left(90)
        first_start = 2

    t.right(angle)
    t.pendown()
    t.forward(60)
    time.sleep(1)
    t.undo()
    t.penup()
    t.goto(0,0)
    angle += 360/60

turtle.done()
