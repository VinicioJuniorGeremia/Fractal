# Fractal

#TRIANGULO
```javascript
import turtle

for i in range(1):
    turtle.pensize(5)
    turtle.left(60)
    turtle.forward(200)
    turtle.right(60)
    turtle.right(60)
    turtle.forward(200)
    turtle.right(120)
    turtle.forward(200)
```
#ESTRELA
```javascript
import turtle

for i in range(1):
    turtle.pensize(5)
    turtle.color("green")
    turtle.left(60)
    turtle.forward(300)
    turtle.right(120)
    turtle.forward(300)
    turtle.right(150)
    turtle.forward(350)
    turtle.right(150)
    turtle.forward(300)
    turtle.right(150)
    turtle.forward(345)
```

#ESPIRAL
```jaavscript
import turtle

for i in range(0, 650, 10):
    turtle.pensize(5)
    turtle.speed(100)

    turtle.forward(i)
    turtle.left(90)
```

#FLOCO DE NEVE
```javascript
import turtle

#Config. screen
WIDTH, HEIGHT = 1366, 650
screen = turtle.Screen()
screen.setup(WIDTH, HEIGHT)
screen.screensize(2*WIDTH, 2*HEIGHT)
screen.bgcolor('black')
screen.delay(0)

#Config. Turtle
trig = turtle.Turtle()
trig.pensize(2)
trig.speed(1)
trig.setpos(-WIDTH // 6, HEIGHT // 6)
trig.color('gold')

# L-system
generation = 5
axiom = 'F++F++F'
chr_1, rule_1 = 'F', 'F-F++F-F'
chr_2, rule_2 = 'G', 'GG'
step = 300
angle = 60

def apply_rules(axiom):
    return ''.join([rule_1 if chr == chr_1 else chr for chr in axiom])

for gen in range(generation):
    turtle.pencolor('white')
    turtle.goto(-WIDTH // 2 + 60, HEIGHT // 2 - 100)
    turtle.clear()
    turtle.write(f'Geração: {generation}', font=('Arial', 60, "normal"))

    trig.setheading(0)
    trig.goto(-WIDTH // 6, HEIGHT // 6)
    trig.clear()

    length = step / pow(3, gen)

    for chr in axiom:
        if chr == chr_1:
            trig.forward(length)
        elif chr == '+':
            trig.right(angle)
        elif chr == '-':
            trig.left(angle)

    axiom = apply_rules(axiom)
```

#ARVORE
```javascript
import turtle

turtle.bgcolor("black")
arv = turtle.Turtle()
arv.pensize(2)
arv.color("green")
arv.left(90)
arv.backward(100)
arv.speed(999)

def drawTree(i):
    if i < 10:
        print("Inside")
        return
    else:
        print("Quitside")
        arv.forward(i)
        arv.color("magenta")
        arv.circle(2)
        arv.color("brown")
        arv.left(30)
        drawTree(3*i/4)
        arv.right(60)
        drawTree(3*i/4)
        arv.left(30)
        arv.backward(i)

drawTree(100)
turtle.done()
```