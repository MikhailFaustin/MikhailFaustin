- 👋 Hi, I’m @MikhailFaustin
- 👀 I’m interested in ...
- 🌱 I’m currently learning Python
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me on Discord. My nickname and tag is Cave Johnson#1436

<!---
MikhailFaustin/MikhailFaustin is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import pygame
from player import Player
from settings import *

pygame.init()
sc = pygame.display.set_mode((WIDTH, HEIGHT))
clock = pygame.time.Clock()
player = Player()


while True:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            exit()
    player.movement()
    sc.fill(BLACK)


    pygame.draw.circle(sc, WHITE, (int(player.x), int(player.y)), 12)
    #pygame.draw.line(sc, GREEN, player.pos, (player.x + WIDTH * math.cos(player.angle),
    #                                         player.y + WIDTH * math.sin(player.angle)), 2)
    #    pygame.draw.rect(sc, DARKGRAY, (x, y, TILE, TILE), 2)

    pygame.display.flip()
    clock.tick(FPS)
    # print(clock.get_fps())
    
    import pygame
from nastroiki import *

class Player:
    def __init__(self):
        self.pos = Player
        self.x, self.y = player_pos
        self.angle = player_angle

        def movement(self):
            keys = pygame.key.get_pressed()
            if keys[pygame.K_w]:
                self.y -= player_speed
            if keys[pygame.K_s]:
                self.y += player_speed
            if keys[pygame.K_a]:
                self.x -= player_speed
            if keys[pygame.K_d]:
                self.x += player_speed
            if keys[pygame.K_LEFT]:
                self.angle -= 0.02
            if keys[pygame.K_RIGHT]:
                self.angle += 0.02

    def movement(self):
        pass
        
 from nastroiki import *

text_map = [
    'WWWWWWWWWWWWWWWWWWWW',
    'WW.................W',
    'WW....WW..WWWWWWWW.W',
    'WW....WW...........W',
    'WW....WW..W...W....W',
    'WW....WW..WWWWWWWW.W',
    'WW....WW...........W',
    'WW....WW..WWWWWWWW.W',
    'WW.................W',
    'WW..WWWWWWW..WWWW..W',
    'WW.................W',
    'WWWWWWWWWWWWWWWWWWWW',

]

world_map = set()
for j, row in enumerate(text_map):
    for i, char in enumerate(row):
        if char == 'W':
            world_map.add((i * TILE, j * TILE))

# game nastroiki
WIDTH = 1200
HEIGHT = 800
HALF_WIDTH = WIDTH // 2
HALF_HEIGHT = HEIGHT // 2
FPS = 60
TILE = 100

# player nastroiki
player_pos = (HALF_WIDTH, HALF_HEIGHT)
player_angle = 0
player_speed = 2

# colors
WHITE = (255, 255, 255)
BLACK = (0, 0, 0)
RED = (220, 0, 0)
GREEN = (0, 0, 220)
DARKGRAY = (110, 110, 110)
PURPLE = (120, 0, 120)
