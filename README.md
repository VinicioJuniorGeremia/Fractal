# Fractal

| O que é um Fractal?

Um fractal é um objeto geométrico que exibe uma estrutura semelhante em diferentes escalas. Em outras palavras, um fractal é uma figura que é composta por partes menores que se assemelham à figura como um todo. Essas partes menores também têm a mesma complexidade da figura original, e essa repetição de padrões se repete infinitamente em diferentes escalas.

| Onde eles podem ser encontrados?

Os fractais podem ser encontrados em muitos lugares da natureza, como em flores, nuvens, montanhas, rios e até mesmo no nosso sistema circulatório. Eles também são usados em muitas áreas da ciência, como na física, matemática, biologia, economia e computação gráfica.

| A partir disso, podemos desenhar gráficos fractais, utilizando a biblioteca Turtle...
A biblioteca Turtle é uma biblioteca gráfica em Python que permite desenhar figuras geométricas na tela do computador usando comandos simples.

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
//Importa a biblioteca Turtle para o código.
#Config. screen
WIDTH, HEIGHT = 1366, 650
screen = turtle.Screen()
screen.setup(WIDTH, HEIGHT)
screen.screensize(2*WIDTH, 2*HEIGHT)
screen.bgcolor('black')
screen.delay(0)
//Configura as dimensões da tela de exibição, bem como a cor do fundo. O delay(0) faz com que a animação seja executada o mais rapidamente possível.
#Config. Turtle
trig = turtle.Turtle()
trig.pensize(2)
trig.speed(1)
trig.setpos(-WIDTH // 6, HEIGHT // 6)
trig.color('gold')
//Cria um turtle chamada "trig", que será usada para desenhar o fractal. Define algumas características da tartaruga, como a largura da caneta, a velocidade e a posição inicial.
# L-system
generation = 5
axiom = 'F++F++F'
chr_1, rule_1 = 'F', 'F-F++F-F'
chr_2, rule_2 = 'G', 'GG'
step = 300
angle = 60
//Define uma L-system: a quantidade de gerações, o axioma inicial, dois caracteres possíveis (F e G), e duas regras de substituição. O comprimento do passo e o ângulo de rotação são definidos para desenhar a L-system.
def apply_rules(axiom):
    return ''.join([rule_1 if chr == chr_1 else chr for chr in axiom])
//A função apply_rules recebe uma string como entrada e aplica as regras de substituição definidas na L-system.
for gen in range(generation):
    turtle.pencolor('white')
    turtle.goto(-WIDTH // 2 + 60, HEIGHT // 2 - 100)
    turtle.clear()
    turtle.write(f'Geração: {generation}', font=('Arial', 60, "normal"))

    trig.setheading(0)
    trig.goto(-WIDTH // 6, HEIGHT // 6)
    trig.clear()

    length = step / pow(3, gen)
//O loop principal do programa itera sobre cada geração da L-system. Dentro do loop, o título da geração atual é exibido na tela usando o método write da biblioteca Turtle. Em seguida, a posição inicial da tartaruga é redefinida, o comprimento do passo é recalculado e a tartaruga é reposicionada no início.
    for chr in axiom:
        if chr == chr_1:
            trig.forward(length)
        elif chr == '+':
            trig.right(angle)
        elif chr == '-':
            trig.left(angle)

    axiom = apply_rules(axiom)
//O loop interno itera sobre cada caractere da string do axioma e move a tartaruga de acordo com as regras da L-system. O axioma é atualizado aplicando as regras de substituição definidas na função apply_rules.
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