# Projektadarbs
hellooo
..
wn.listen()

wn.onkeypress(go_up, "w")

wn.onkeypress(go_down, "s")

wn.onkeypress(go_left, "a")

wn.onkeypress(go_right, "d")

while True:

wn.update()


if head.xcor()>290 or head.xcor()<-290 or head.ycor()>290 or head.ycor()<-290:

time.sleep(1)

head.goto(0,0)

head.direction = "stop"

for segment in segments:

segment.goto(1000, 1000)



segments.clear()


score = 0


delay = 0.1

pen.clear()

pen.write("Score: {} High Score: {}".format(score, high_score), align="center", font=("Courier", 24, "normal"))


if head.distance(food) < 20:


x = random.randint(-290, 290)

y = random.randint(-290, 290)

food.goto(x,y)


new_segment = turtle.Turtle()

new_segment.speed(0)

new_segment.shape("square")

new_segment.color("red")

new_segment.penup()

segments.append(new_segment)


delay -= 0.001

#punkti

score += 10

if score > high_score:

high_score = score


pen.clear()

pen.write("Score: {} High Score: {}".format(score, high_score), align="center", font=("Courier", 24, "normal"))


for index in range(len(segments)-1, 0, -1):

x = segments[index-1].xcor()

y = segments[index-1].ycor()

segments[index].goto(x, y)


if len(segments) > 0:

x = head.xcor()

y = head.ycor()

segments[0].goto(x,y)

move()

for segment in segments:

if segment.distance(head) < 20:

time.sleep(1)

head.goto(0,0)

head.direction = "stop"


for segment in segments:

segment.goto(1000, 1000)


segments.clear()


score = 0

# Reset the delay

delay = 0.1


# Update the score display

pen.clear()

pen.write("Score: {} High Score: {}".format(score, high_score), align="center", font=("Courier", 24, "normal"))

time.sleep(delay)

wn.mainloop()
