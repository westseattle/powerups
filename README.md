# Platform Game

Adding Powerups and Hazards to Your Platform Game

So you have a character jumping around. That isn't very interesting. The Hero needs some enemies, some hazards. How would we make a pit for the Hero to fall into? 

## Hazards

Those that cost a player health, and those that cost a player their life. Will want to keep track of the player's lives. At the beginning of the game, lets create a variable to store the number of lives. Each time the player dies, we can broadcast a message to subtract a life. One variable that keeps track of a player's health, let's say the player has a health bar with 3 hearts. Lose all hearts, you lose a life. 

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
