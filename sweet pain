import pygame
import math #needed for square root function
isBig = False

#initializes Pygame
pygame.init()
print(pygame.font.get_fonts())
pygame.display.set_caption("Cookie Clicker")#sets the window title
screen = pygame.display.set_mode((400,400))#creates game screen

#player variables
xpos = 0
ypos = 0
mousePos = (xpos, ypos) #variable mousePos stores TWO numbers
numClicks = 0

#circle variables: circX and circY are the coordinates of the center (where it's drawn), and the radius is how big it is
circX = 50
circY = 50
radius = 100

CookiePic = pygame.image.load("skull.png")
CookieRect = CookiePic.get_rect(topleft=(100,100))

font = pygame.font.Font('freesansbold.ttf', 32)
text1 = font.render('score:', False, (0, 200, 200))
text2 = font.render(str(int(numClicks)), 1, (0, 200, 200))

#gameloop###################################################
while True:
#event queue (bucket that holds stuff that happens in game and passes to one of the sections below)
    event = pygame.event.wait()

    if event.type == pygame.QUIT: #close game window
        break

    if event.type == pygame.MOUSEBUTTONDOWN: #check if clicked
      if math.sqrt((mousePos[0] - 200)**2+(mousePos[1] - 200)**2)<radius:
            numClicks+=1
            print("adding score")
      print("CLICK")
      CookieRect.y+=20
    if CookieRect.y > 100:
        CookieRect.y -=5
    if event.type == pygame.MOUSEMOTION: #check if mouse moved
        mousePos = event.pos #refreshes mouse position
        #print("mouse position: (",mousePos[0]," , ",mousePos[1],")")
        if math.sqrt((mousePos[0] - 200)**2+(mousePos[1] - 200)**2)<radius:
            isBig = True
        else:
            isBig = False
 
#render section---------------------------------------------
    screen.fill((100, 100, 100)) #wipe screen (without this, things smear)
    screen.blit(CookiePic, CookieRect)
    #pygame.draw.circle(screen, (200, 0, 200), (200,200), radius)    
    text2 = font.render(str(int(numClicks)), 1, (0, 200, 200))
    screen.blit(text1, (10, 10))
    screen.blit(text2, (110, 10))
    
    #print("clicks:", numClicks) #uncomment this once collision is set up
        
    pygame.display.flip()
    

#end game loop##############################################

pygame.quit()



