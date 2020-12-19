# CMPT306_Purification
A 2D platform game created by unity3D.
Completed as a group project in University of Saskatchewan CMPT 306 class

Group Project Proposal

Overview
Our game is a 2D platformer game which is called Purification. The object of the game is to purify the forest by killing the undead army. The game will include three level of adventures - easy, medium, and hard. In each level, rewards and power-up materials will be provided on your way. In order to succeed in the game, except killing the undead, you have to avoid the attacks and attachment by your enemies to keep alive. 

GamePlay
The main character is represented as an archer. The player controls the archer by using the A and D keys to turn left or right, and W to jump.
The archer also has weapon - bow and arrow. The player can use the space key to shoot and use the mouse to adjust the shooting angle.
The enemy is represented as the undead. When a player’s arrow collides with the undead, the enemy’s HP will be reduced. The undead is destroyed completely if their HP drops to 0.
The rewards are represented as crystals. Crystals will drop on the ground after an enemy has been killed, and can be picked up if the archer move to touch them. The crystals will turn into money once they are collected. The amount of money is displayed on the top-right corner of the screen.
The NPC characters are represented as a colorful cubes. After finding them, the player can use his money to upgrade the weapon by simply clicking on the cubs.
A big boss will appear at the end of each level. Win if the boss is destroyed. 

Features
Controls
Basic Actions: move towards left/right,  jump.
The ability to shoot adjust shooting angle.
The ability to gain rewards, and exchange for power-up materials.
Boss and NPC
At the end of each level, the protagonist will meet a boss which has their unique attack style and once their health loss to a specific point , they will change their attack style and output higher damage.
With the level-up, the boss will become harder.
NPC in each level, the protagonist can upgrade the weapon through them.
Information Display:
How many coins gained, the HP, ATTACK , DEFENSE of the protagonist, the information of weapon ,skills the protagonist had will be displayed on the lower left corner of the screen.
HP
Once the HP runs out , the player loses the game, and can retry from the beginning of this level.
The protagonist's maximum HP starts at 20 and only increases when their LV does.
After defeating the boss of this level, the protagonist fully heals and raise the protagonist's HP 10 points above its cap. HP can also be restored through consumable items (eat food and use medicine).
An attack hitting the receiving party lowers their HP. The loss is dependent on the attacking party's Attack and the party of receipt Defense. Upon reaching 0 HP, the protagonist will be displayed in a dead form , sending them to the GAME OVER screen and asking them want to retry or not. If a monster's HP reaches 0, they disintegrate into dust and reward the protagonist with power-up, food, coins, health.
ATTACK(AT):
AT determines the damage output of the attacking party. The protagonist's base AT increases with LV and equipping a weapon. AT can be changed temporarily during battles with actions or consumables.
DEFENSE(DF):
DF determines the damage input for the defending party. The protagonist's base DF increases with Level and equipping armor. DF can be changed temporarily during battles with certain actions or consumables.
DF is subtracted from the damage output of the attacking party. However, it cannot lower the taken damage to a value less than 1.

Technical Challenges
Dynamic Physics
In order to make the action realistic, we need to set up the enemy body type first, static, kinematic or dynamic, dynamic body type will be primary uses, set up the mass, linear drag and so on very carefully. Then set up the 2D collider, unity support 4 different kinds of collider assembly, we can use different assembly apply to a different enemy.
For the enemies’ movements, we need to set up enemy walk speed and collision detection system to deduct player health, each enemy needs to provide at least two animations with specific names, such as walkAnim and hitAnim. Some enemy basic behavior is to move in one direction until they encounter a particular identification that indicates that they should change direction. So we need to set up a check function check if the enemy encounters a hit by the player, if not, change the direction to the opposite. Some enemy behavior is to move towards to the player. After sometimes, pause, and continue repeating this way, we may set up the walk speed first, and also set up a stop time.
Different animation should also be set up for different attack styles. For example, if the boss shoots some razer from the ground, we need to write some code choose the spot of the razer spawns, the code should choose the random spot around the players, like randomRadius(100), in order to avoid too many razors spawns on the same spot and so on.
Level Editing
First, at the begin of the game, we will read a default value to make sure how difficulty the player want to play. With easier difficulty, the protagonist starts with higher HP, AT and DF while the enemies will have lower HP, AT and DF as well as a lower frequency they appear, at the same time, the damage range of them shrinks.
Second, with protagonist's properties(HP, DF, AT) increase after every level-up, the enemies properties also improved, the range of protagonist's shooting and the damage range of enemies both expand ,which makes the game harder.
Artificial Intelligence (AI)
By going through the game, the level of the game will increase, one of the ways to achieve it is to level up the enemy, by not only focus on the health and attack strength, but also the ability of the enemy, such as a level 10 enemy and a level 5 enemy will have two different ability: Level 5: search-attack-die; Level 10: search-skill attack-attack-run-die. As to doing that, we will need to write a basic AI logic: search-attack-die, and embed a variety of abilities in it to achieve AI type diversity.
And as we mentioned in the basic features: when defeating every boss at the end of each level, once the boss loses health to a specific point, they will do more defense which means every single attack the protagonist makes will cause less damage. Also the boss can identity which kind of skills you used to make a better defense, meanwhile they can change their fixed attack pattern to a random, unpredictable one.

Usability/playability Testing
After completion, firstly, we are going to test the game by ourselves. Judgment could be based on the performance of the game, such as loading speed, characters’ reactions, movements, etc. If the game runs bug-free with good performance quality, we are going to test its playability with people from different ages. Later on, further adjustment will be applied based on their feedbacks, for example, the operations are easy or difficult and the game itself is fun or not. 

Design challenge
Animations for Death
After the player or an enemy is killed, we are going to use shader to make object dissolving, that is, letting this model fade away. The easiest way to directly let his pixel’s fragment shader operate discard might let this pixel disappears. Then we will let one part of the object disappear and the other exists.
level of the game
In order to make a game level balances, we need to go through four cycle
Determine the difficulty relationship
Identify the elements in each level
Putting enemy on the map
Testing the game
