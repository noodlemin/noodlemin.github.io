---

layout: single
title: Python Game - Notes
typora-root-url: ../
categories: Learning
tags: Project Game Python
toc: true

---
# Environment

- Event Loop handles asynchronous events, e.g., tracking keyboard inputs and moving a character.

- The clock object controls the frame rate of the game and calculates the time elapsed since the last frame using the `tick()` method. This approach helps in achieving consistent frame rates and smooth gameplay.

# Character

- The coordinate origin is the top-left corner. For example, if you want to draw a character with a size of 10x10 (width x height) in the center of a screen with a size of 100x100, the character's position should be calculated as follows:
  - ((100/2) - (10/2), (100/2) - (10/2)) = (45, 45)


- In the tutorial, they use 'event.keydown' to move the character, but I prefer using 'pygame.key.get_pressed()' because it allows for simultaneous input and I believe it is more suitable for moving the character.

# Weapon
  - Unlike the character, allowing simultaneous input for the weapon may result in firing the weapon without delay. Therefore, I need to add a weapon cooldown mechanism to prevent this, ensuring that projectiles are created only after a certain amount of time has passed.
