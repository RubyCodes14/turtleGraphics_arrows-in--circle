# turtleGraphics_arrows-in--circle

#   the start point is 0, 0
#   the subsequent start point is the current pen location
#
#

import turtle

sc = turtle.getscreen()
sc.bgcolor("#F1F1F1")

turtle.write("Refer to your console window")

rad2 = input("Specify the size of display in pixels[Min. 50] \nor press ENTER to use default size \nEnter Here: ")
if rad2 == "":
    rad2 = 200              #inner circle
elif rad2.isdigit():
    rad2 = int(rad2)
else:
    print("ERROR...")
    rad2 = False
if rad2:
    print("Check your \'Python Turtle Graphics\' Window for the display.")
    
rad1 = rad2 + rad2/4    #or simplry 3rad2/2 for outer circle
outline1 = "red"
outline2 = "yellow"
fill_1 = "red"
fill_2 = "yellow"

arrow1 = "black"
arrow2 = "red"

start_x = rad1 * 58/100
start_y = rad1 * 26/100

arrowWidth = int(rad2/4 - (rad2 * 3/100) + (rad2 * 2/100))
arrowHead = int(arrowWidth * 2 + (rad2 * 1.5/100))
arrowHeight = rad2 

#first
#    outer circle - rad1
turtle.color(outline1, fill_1)
turtle.penup()
turtle.goto(0, -rad1)       #this will always align the circle at centre
turtle.pendown()
turtle.begin_fill()
turtle.circle(rad1)
turtle.end_fill()

#second
#     inner circle - rad2
turtle.color(outline2, fill_2)
turtle.penup()
turtle.goto(0, -rad2)       #this will always align the circle at centre
turtle.pendown()
turtle.begin_fill()
turtle.circle(rad2)
turtle.end_fill()

#first
#   arrow1 - consider second circle, rad2
turtle.color(arrow1, arrow1)
turtle.penup()
turtle.goto(-start_x, -start_y)     #(x, y)
turtle.pendown()
turtle.begin_fill()
turtle.forward(arrowWidth)
turtle.left(90)
turtle.forward(arrowHeight)
turtle.right(90)
turtle.forward(arrowWidth - 4)
turtle.right(90)
turtle.forward(arrowHeight)
turtle.left(90)
turtle.forward(arrowWidth)
turtle.right(135)
turtle.forward(arrowHead)
turtle.right(90)
turtle.forward(arrowHead)
turtle.end_fill()

turtle.right(315)       #returns turtle to normal direction - i.e horizontal right

#second
#    arrow2
turtle.color(arrow2, arrow2)
turtle.penup()
turtle.goto(start_x, start_y)     #(x, y)
turtle.pendown()
turtle.begin_fill()
turtle.forward(arrowWidth)
turtle.left(90)
turtle.forward(arrowHeight)
turtle.right(90)
turtle.forward(arrowWidth - 4)
turtle.right(90)
turtle.forward(arrowHeight)
turtle.left(90)
turtle.forward(arrowWidth)
turtle.right(135)
turtle.forward(arrowHead)
turtle.right(90)
turtle.forward(arrowHead)
turtle.end_fill()


turtle.penup()
turtle.goto(0, -(rad2 + 200))
turtle.done()


