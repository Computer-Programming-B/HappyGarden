![](HappyGarden.gif)   
Happy Garden
===========
When this game starts, a cow with a watering can appears in the garden, but there is only one flower. Every few seconds another flower appears or an existing flower begins to wilt. Use the arrow keys to move the cow to the wilted flowers and press the space bar to water them. If any flower remains wilted for more than ten seconds, the game ends. But if the garden is happy for more than 15 seconds, one of the flowers mutates into a fangflower and tries to zap the cow.

Suggested steps to get started:
---------------------------------
1. Start by forking [this replit](https://replit.com/@MrSimonLowell/HappyGardenBase), or download and unzip the replit if you are working on your own PC or Mac.
2. This is the largest and most complicated project of the semester. To help keep it manageable, we'll start with an outline that labels each variable and function that we need to complete to finish the program. After each step, run your program to check for errors. *Keep your program running!* Don't go to the next step until you've fixed the errors on the current step.
3. We'll start by drawing the garden and the cow. Under the comment `#screen dimension variables` add the following code:
    ```python
    #screen dimension variables
    WIDTH = 800
    HEIGHT = 600
    ```
    Then in the `draw()` function, replace the placeholder `pass` with:
    ```python
    def draw():
        screen.blit("garden",(0,0))
    ```
    Run your code, you should see the garden.   

4. Next, we'll add the cow. Under the comment `#actor variables` add the following code:
    ```python
    #actor variables
    cow = Actor("cow")
    cow.pos = 100, 500
    ```
    Then in the `draw()` function, draw the cow after the garden:
    ```python
    def draw():
        screen.blit("garden",(0,0))
        cow.draw()
    ```
    Run your code, you should see the cow with the watering can in the bottom left hand corner of the garden.   

5. Now we'll make the cow move. In the `update()` function, replace the placeholder `pass` with:
    ```python
    def update():
        if(keyboard.left and cow.x > 0):
          cow.x -= 5
        if(keyboard.right and cow.x < WIDTH):
          cow.x += 5
        if(keyboard.up and cow.y > 150):
          cow.y -= 5
        if(keyboard.down and cow.y < WIDTH):
          cow.y += 5
    ```
    Run your code and click on the screen with the mouse. You should be able to move the cow around the garden with the arrow keys.   

6. Next, we'll have the cow use the watering can when we press the space bar. In the `reset_cow()` function, replace the placeholder `pass` with:
    ```python
    def reset_cow():
        cow.image = "cow"
    ```
    Now add the following code to `update()`:
    ```python
    def update():
      if(keyboard.space):
        cow.image = "cow-water"
        clock.schedule(reset_cow, 0.5)
      if(keyboard.left and cow.x > 0):
        cow.x -= 5
      if(keyboard.right and cow.x < WIDTH):
        cow.x += 5
      if(keyboard.up and cow.y > 150):
          cow.y -= 5
      if(keyboard.down and cow.y < WIDTH):
          cow.y += 5
    ```
7. *More to come*    

Extensions
----------------------------------------------
**Add sounds**. Create a `sounds` folder like the one in the previous assingment. Play appropriate sounds for each action in the game. Unfortunately, replit doesn't support sounds in Pygame.  

**Change the gardener**. In the image folder there is an alternate picture of a pig with a watering can. You can use that or make a new character using any 8-bit online editor.   

**Add more flowers**. You can change how often a new flower appears on the screen to make the game easier or harder. Update the code under `def add_flowers():` to change how often it schedules a call to itself.   

**Faster fangflowers**. You can make the fangflowers move faster by changing the possible range of `random_velocity`. Try increasing the range by using something like `randint(4,6)`.   

**Add more fangflowers**. Is the game to hard or too easy? You can change the code in `mutate()` to make fangflowers appear more or less often.   

**Add new enemies**. If you find the game is not challenging enough at the moment, you can add more enemies. 

**Rain in the garden**. What happens if it rains in the garden? The flowers will be much happier and wouldn't need watering. But they will also mutate into fanglowers more quickly. To make it look like it's raining, you can update the background with `garden-raining.png` in the images folder.

Samples of Student work
-----------------------
*none yet!*   
   
      
      
      
<p align="center"><i>This project was adapted from the book <b><a href="https://www.dk.com/us/book/9781465473615-coding-games-in-python/">Coding Games in Python</a></b></i></p>
