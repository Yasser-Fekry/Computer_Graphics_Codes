
---
```md
  
   ____                            _               ____                 _     _           
  / ___|___  _ __ ___  _ __  _   _| |_ ___ _ __   / ___|_ __ __ _ _ __ | |__ (_) ___ ___  
 | |   / _ \| '_ ` _ \| '_ \| | | | __/ _ \ '__| | |  _| '__/ _` | '_ \| '_ \| |/ __/ __| 
 | |__| (_) | | | | | | |_) | |_| | ||  __/ |    | |_| | | | (_| | |_) | | | | | (__\__ \ 
  \____\___/|_| |_| |_| .__/ \__,_|\__\___|_|     \____|_|  \__,_| .__/|_| |_|_|\___|___/ 
                      |_|                                        |_|
```

---
```Python

# Create Window by Pygame 

import pygame
pygame.init()
screen = pygame.display.set_mode((800,600))
Running = True
while Running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            Running = False
    screen.fill((255,255,255))
    pygame.display.flip()
pygame.quit()
```

---
```python
# Create Shapes by Pygame 

import pygame
pygame.init()
screen = pygame.display.set_mode((800,600))
screen.fill((255,255,255))
R = (255,0,0)
B = (0,0,255)
# rect مربع
pygame.draw.rect(screen , B , (50,50,200,100))
pygame.draw.circle(screen , R , (100,230) , 50 )
pygame.draw.line(screen , R , (50,300) , (250,300) , 10)
pygame.display.flip()
pygame.time.wait(50000)
pygame.quit()

```

---
```Python
# Scale For Image 
import pygame
pygame.init()
screen = pygame.display.set_mode((600,400))
pygame.display.set_caption("Test")
image = pygame.image.load("test.png")
Running = True
while Running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            Running = False
    screen.fill((255,255,255))
    screen.blit(image,(100,50))
    pygame.display.flip()
pygame.quit()
```
---
```Python 
# Creat Window By OpenGL
from OpenGL.GL import *
from OpenGL.GLUT import *
import sys

def draw():
    glClear(GL_COLOR_BUFFER_BIT)
    glFlush()

glutInit(sys.argv)
glutInitDisplayMode(GLUT_SINGLE | GLUT_RGB)
glutInitWindowSize(640, 480)
glutInitWindowPosition(100, 100)
glutCreateWindow(b"Test Window")
glClearColor(1.0, 1.0, 1.0, 1.0)
glutDisplayFunc(draw)
glutMainLoop()

```

---
```Python
# Creat Point By Open GL

from OpenGL.GL import *
from OpenGL.GLUT import *
import sys

def draw():
    glClear(GL_COLOR_BUFFER_BIT)
    glFlush()

glutInit(sys.argv)
glutInitDisplayMode(GLUT_SINGLE | GLUT_RGB)
glutInitWindowSize(640, 480)
glutInitWindowPosition(100, 100)
glutCreateWindow(b"Test Window")
glClearColor(1.0, 1.0, 1.0, 1.0)
glutDisplayFunc(draw)
glutMainLoop()
```

---
```Python
# Create Line  By OpenGL
from OpenGL.GL import *
from OpenGL.GLUT import *
from OpenGL.GLU import *
import sys

def draw():
    glClear(GL_COLOR_BUFFER_BIT)
    glColor3f(0.0, 0.0, 1.0)
    glLineWidth(3)
    glBegin(GL_LINES)
    glVertex2f(100, 240)
    glVertex2f(540, 240)
    glEnd()
    glFlush()

glutInit(sys.argv)
glutInitDisplayMode(GLUT_SINGLE | GLUT_RGB)
glutInitWindowSize(640, 480)
glutInitWindowPosition(100, 100)
glutCreateWindow(b"Test Window")
glClearColor(1.0, 1.0, 1.0, 1.0)

glMatrixMode(GL_PROJECTION)
glLoadIdentity()
gluOrtho2D(0, 640, 0, 480)

glutDisplayFunc(draw)
glutMainLoop()
```

---
```Python
# Creat tringle by OpenGL
from OpenGL.GL import *
from OpenGL.GLUT import *
from OpenGL.GLU import *
import sys

def draw():
    glClear(GL_COLOR_BUFFER_BIT)
    glColor3f(1.0, 0.0, 0.0)
    glBegin(GL_TRIANGLES)
    glVertex2f(320, 380)
    glVertex2f(220, 180)
    glVertex2f(420, 180)
    glEnd()
    glFlush()

glutInit(sys.argv)
glutInitDisplayMode(GLUT_SINGLE | GLUT_RGB)
glutInitWindowSize(640, 480)
glutInitWindowPosition(100, 100)
glutCreateWindow(b"Test")
glClearColor(1.0, 1.0, 1.0, 1.0)

glMatrixMode(GL_PROJECTION)
glLoadIdentity()
gluOrtho2D(0, 640, 0, 480)

glutDisplayFunc(draw)
glutMainLoop()
```

---
```Python
# Create Square By Open GL
from OpenGL.GL import *
from OpenGL.GLUT import *
from OpenGL.GLU import *
import sys

def draw():
    glClear(GL_COLOR_BUFFER_BIT)
    glColor3f(1.0, 0.0, 0.0)

    glBegin(GL_QUADS)
    glVertex2f(220, 180)
    glVertex2f(420, 180)
    glVertex2f(420, 380)
    glVertex2f(220, 380)
    glEnd()

    glFlush()

glutInit(sys.argv)
glutInitDisplayMode(GLUT_SINGLE | GLUT_RGB)
glutInitWindowSize(640, 480)
glutInitWindowPosition(100, 100)
glutCreateWindow(b"Square Outline")
glClearColor(1.0, 1.0, 1.0, 1.0)

glMatrixMode(GL_PROJECTION)
glLoadIdentity()
gluOrtho2D(0, 640, 0, 480)

glutDisplayFunc(draw)
glutMainLoop()

```

---
```Python
# Function For DDA Algorithm 
import pygame
import sys
def dda(screen, x1, y1, x2, y2, color):
    dx = x2 - x1
    dy = y2 - y1
    steps = int(max(abs(dx), abs(dy)))
    x_inc = dx / steps
    y_inc = dy / steps
    x = x1
    y = y1
    for _ in range(steps + 1):
        screen.set_at((round(x), round(y)), color)
        x += x_inc
        y += y_inc
```

---
```Python 

# ---- Main Program ----
pygame.init()
screen = pygame.display.set_mode((640, 480))
pygame.display.set_caption("DDA Line Drawing")
screen.fill((255, 255, 255))  
dda(screen, 100, 100, 500, 300, (255, 0, 0)) 
pygame.display.flip()
while True:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()
```

---
```Python

#  Function Bresenham Algotithm 
def bresenham(screen, x1, y1, x2, y2, color):
    dx = abs(x2 - x1)
    dy = abs(y2 - y1)
    x, y = x1, y1

    sx = 1 if x2 > x1 else -1
    sy = 1 if y2 > y1 else -1

    if dy <= dx:
        err = dx // 2
        while x != x2:
            screen.set_at((x, y), color)
            err -= dy
            if err < 0:
                y += sy
                err += dx
            x += sx
        screen.set_at((x, y), color)
    else:
        err = dy // 2
        while y != y2:
            screen.set_at((x, y), color)
            err -= dx
            if err < 0:
                x += sx
                err += dy
            y += sy
        screen.set_at((x, y), color)
```

---
