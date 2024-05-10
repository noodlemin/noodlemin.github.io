---

layout: single
title: Pygame - Super Buster Bros (Pang)
typora-root-url: ../
categories: Learning
tags: Project Game Python
toc: true

---

# Summary

- I gained a deeper understanding of object-oriented programming (OOP) concepts, including classes and inheritance. For instance, I created a Ball class and utilized inheritance to incorporate specific attributes and behaviors from the Ball class into different types of balls with unique features.

# Plan

## Make the game

- <iframe width="320" height="240" src="https://www.youtube.com/embed/d6rJctconM0?si=fDzTW7soY3Lszd1U" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

- Tutorial source: [파이썬 코딩 무료 강의 (활용편1) - 추억의 오락실 게임을 만들어 보아요. 3시간이면 충분합니다. [나도코딩\] (youtube.com)](https://www.youtube.com/watch?v=Dkx8Pl6QKW0)

- Tools
  - Pygame
  
- Conditions
  - Goal
    - The character fires the weapon to remove all balloons within a time limit while also avoiding being hit by them.
  - Character
    - Movement is limited to left and right.
    - The space bar fires the weapon, and the projectile travels only vertically.
  - Balloons
    - A single large balloon is dropped from the top.
    - If hit by the projectile, it splits into two smaller balloons.
    - There are four sizes of balloons, with bouncing behavior.
    - The smallest balloons are removed when hit by the projectile.
  
- Structure
  
  - The tutorial did not use classes for creating objects, likely because it's designed for a single-level game. However, to facilitate easy replication of objects for additional levels, I may need to refactor the code to incorporate classes.
  - There is a background and a stage. The character stands on the stage.
  
  - Character
  - Projectile
  - Ballons

## Export the Game to Web

- I can either translate my Python code to JavaScript or utilize a conversion tool.
  - Consider using pygbag, a tool that converts Python code into WebAssembly code.
    - [Export Python pygame Game to Web with WebAssembly (pygbag tutorial) (youtube.com)](https://www.youtube.com/watch?v=q25i2CCNvis)
    - It seems it does not work at least in MacOS.

## Make the game Online

- Either socket or server.

# Notes

## Environment

- Event Loop handles asynchronous events, e.g., tracking keyboard inputs and moving a character.

- The clock object controls the frame rate of the game and calculates the time elapsed since the last frame using the `tick()` method. This approach helps in achieving consistent frame rates and smooth gameplay.

## Character

- The coordinate origin is the top-left corner. For example, if you want to draw a character with a size of 10x10 (width x height) in the center of a screen with a size of 100x100, the character's position should be calculated as follows:
  - ((100/2) - (10/2), (100/2) - (10/2)) = (45, 45)


- In the tutorial, they use 'event.keydown' to move the character, but I prefer using 'pygame.key.get_pressed()' because it allows for simultaneous input and I believe it is more suitable for moving the character.

## Weapon

  - Unlike the character, allowing simultaneous input for the weapon may result in firing the weapon without delay. Therefore, I need to add a weapon cooldown mechanism to prevent this, ensuring that projectiles are created only after a certain amount of time has passed.

## Balloons

- In the tutorial, enumerate was used to calculate the positions of the balloons, but since the index wasn't necessary, I opted for a standard for loop instead.
- To avoid potential crashes in the game, I utilized the `get` method to check for values in the dictionary. This prevents the entire game from crashing if certain values from the balloons cannot be retrieved.
- In the tutorial, it computes the sizes of balloons while calculating their positions, but I opted to store the size separately and load it. Although there seems to be no performance difference, I chose this approach for consistency and ease of maintenance.
  - before: ![image-20240502113407824](/assets/images/2024-04-24-pygame-sbb/image-20240502113407824.png) 
  - after:![image-20240502113649936](/assets/images/2024-04-24-pygame-sbb/image-20240502113649936.png)
- Unlike the tutorial, I use the flag to escape the nested for loops

  



