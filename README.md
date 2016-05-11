# Platform Game

Adding Powerups and Hazards to Your Platform Game

So you have a character jumping around. That isn't very interesting. The Hero needs some enemies, some hazards. How would we make a pit for the Hero to fall into? 

## The Importance of Abstraction

We learned about the concept of abstraction when discussing custom block commands and reporters. Custom blocks allow you to combine multiple steps into a single named block of code. If you write your entire game in a straight line, it will get very long and complicated. If you find that making a simple change to your game logic involves changing the same value in multiple places. Or if it is hard to find a section of your program. Think if a book had no chapters, paragraphs, or indentations. It would just be a big wall of text. A good program should be divided into named sections that make it easy to follow. 

We will create a couple of custom blocks when dealing with hazards and powerups. Since each of these will affect the Hero sprite. 

Pretend you have 10 different powerups and 10 different hazards. Some of these probably have something in common that can be encapsulated into a custom block. For instance, a health powerup and an enemy collision both change the Hero's health. Falling into a lava pit and touching a "1-up" both change the number of lives a player has remaining, even if they change it in opposite ways. 

## Hazards

Hazards are objects, sprites, or positions in the game that cause harm to the Hero. Examples of hazards include Koopa Troopas, lava pits, falling rocks, spikes, knives, bullets, and fire breathing dragons. The level of harm done depends on how you design the hazard. You may decide that falling into a pit costs the Hero a life whereas landing on a spike subtracts 10 "health points". 

Let's create some sprites, variables, and custom blocks for dealing with hazards. 

### Falling into a Pit

A common stationary hazard is a pit that the Hero must jump over. Failing to clear the pit results in the loss of life. Easy enough. We need to keep track of the following:

* __Lives__ - the number of lives will be a variable that stores a number. At the beginning of the game, we can initialize this variable with the number of starting lives in our game. For now, let's choose 3.
* **Visual representaton of the pit** - this will just be a hole in the ground. Simply erase a chunk of the ground so that gravity will make the player fall off the screen under certain conditions. If the player's X and Y positions are within the boundaries of the pit, the player won't reach the ground on the other side. 
* __A custom block to change the number of lives remaining__ - When the player dies, we will want to subtract one from the number of lives. Why do we want this in a custom block? Well, there maybe more than one hazard that takes away the player's life, or there may be a powerup that gives the player another life. We also might want to add a sprite that changes costumes when the player loses a life or execute other code when the number of lives change. Therefore, it is good to combine all of this code into a single block. 

Will want to keep track of the player's lives. At the beginning of the game, lets create a variable to store the number of lives. Each time the player dies, we can broadcast a message to subtract a life. One variable that keeps track of a player's health, let's say the player has a health bar with 3 hearts. Lose all hearts, you lose a life. 

Lives Sprite -> Change costume when receive player died message
Health Sprite -> Change costume when receive player lost health message. How much health? Custom block. Different things make the player lose different amounts of health, so input can vary. Healthbar 100 in increments.
Health sprite should also check if health <= 0, then can broadcast death/change life.

### Pit / Stationary

Lose entire life

A hole in the ground. If we break up the color, the player would keep falling. We could detect if the player's Y position gets below  certain point.

### Moving Enemy

Lose a lot of health, broadcast to health lost touching. 25%.

### Falling

Lose a little health when step on a nail. Broadcast small amount of health lost. 10%

## Powerups

### Medical Kit

Change Health event, increase by 10%

### Extra life

Increase lives

### Invincible

Change health event will not reduce health if powerup applied. Toggle invincible boolean.
