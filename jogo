import pygame
from random import randint


pygame.init()
x = 400
y = 100
pos_x = 80
pos_ya = randint(800, 2000)
pos_yb = randint(800, 2000)
pos_yc = randint(800, 2000)
timer = 0
tempo_segundo = 0

velocidade = 15
velocidade_outros = 30

fundo = pygame.image.load('imagemfundo2.PNG')
carro = pygame.image.load('abelha2.PNG')
bozo1 = pygame.image.load('bozo11.png')
bozo2 = pygame.image.load('bozo22.png')
salles = pygame.image.load('salles1.png')

font = pygame.font.SysFont('arial black', 30)
texto = font.render("Tempo: ", True, (255,255,55), (0,0,0))
pos_texto = texto.get_rect()
pos_texto.center = (65,20)


janela = pygame.display.set_mode((800,600))
pygame.display.set_caption("Criando um jogo com Python")


janela_aberta = True
while janela_aberta :
    pygame.time.delay(50)

    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            janela_aberta = False

    comandos = pygame.key.get_pressed()
    if comandos[pygame.K_UP] and y >= 0:
        y -= velocidade
    if comandos[pygame.K_DOWN] and y <= 500:
        y += velocidade
    if comandos[pygame.K_LEFT]:
        x -= velocidade
    if comandos[pygame.K_RIGHT]:
        x += velocidade

    if (pos_ya <= 0) and (pos_yb <= 0) and (pos_yc <= 0):
        pos_ya = randint(800,1000)
        pos_yb = randint(1300,2000)
        pos_yc = randint(2200,3000)

    if (timer < 20) :
        timer += 1
    else:
        tempo_segundo +=1
        texto = font.render("Tempo: "+str(tempo_segundo), True, (255, 255, 55), (0, 0, 0))
        timer = 0

    pos_ya -= velocidade_outros
    pos_yb -= velocidade_outros + 5
    pos_yc -= velocidade_outros + 2

    janela.blit(fundo, (0,0))
    janela.blit(carro, (x, y))
    janela.blit(salles, (pos_x, pos_yb))
    janela.blit(bozo1, (pos_x + 250, pos_ya))
    janela.blit(bozo2, (pos_x + 500, pos_yc))
    janela.blit(texto, pos_texto)

    pygame.display.update()

pygame.quit()
