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

# Balloons

- In the tutorial, enumerate was used to calculate the positions of the balloons, but since the index wasn't necessary, I opted for a standard for loop instead.
- To avoid potential crashes in the game, I utilized the `get` method to check for values in the dictionary. This prevents the entire game from crashing if certain values from the balloons cannot be retrieved.
- In the tutorial, it computes the sizes of balloons while calculating their positions, but I opted to store the size separately and load it. Although there seems to be no performance difference, I chose this approach for consistency and ease of maintenance.
  - before: ![image-20240502113407824](/assets/images/2024-04-26-pygame-notes/image-20240502113407824.png) 
  - after:![image-20240502113649936](/assets/images/2024-04-26-pygame-notes/image-20240502113649936.png)
