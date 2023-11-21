# MY-FIRST-PROJECT
import pygame
from pygame.locals import *

pygame.init()

# Background
screen = pygame.display.set_mode((800, 600))
bg = pygame.image.load("background.jpg")

# Buttons
play_btn = pygame.image.load("play_btn.png")
quit_btn = pygame.image.load("quit_btn.png")

# Positioning
play_btn_rect = play_btn.get_rect(center=(400, 300))
quit_btn_rect = quit_btn.get_rect(center=(400, 400))

# Display
screen.blit(bg, (0, 0))
screen.blit(play_btn, play_btn_rect)
screen.blit(quit_btn, quit_btn_rect)
pygame.display.update()

# Main game loop
running = True
while running:
    for event in pygame.event.get():
        if event.type == QUIT:
            running = False

        if event.type == MOUSEBUTTONDOWN:
            x, y = event.pos
            if play_btn_rect.collidepoint(x, y):
                print("Play button clicked")
                # Add game start code here
            elif quit_btn_rect.collidepoint(x, y):
                print("Quit button clicked")
                running = False

pygame.quit()
