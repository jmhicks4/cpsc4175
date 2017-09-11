## Homework 4
### By James Hicks
1. An entity class is a class used for storage of information that is long lived inside a database system. A boundary class is a class that is inside of the system while also being on its periphery, it interacts with actors (users) outside of the system. A control class is a class that contains an object that can denote an entity that controls the interactions between a collection of objects.

2. The user will want to play the game, so they will type in their login information into the login screen so that they can login. The login screen will bring them to the map screen where they input the level that they would like to play. They will enter the level that they would like to play and once they have entered a valid level they will be brought to the battle screen. On the battle screen they will move their units, attack if they can, and then end their turn, which will let the enemy do their turn. This will repeat until the player has won or lost, which will return them to the map screen. From the map screen they will be able to choose another battle, save the game, or go to the shop. If they save the game they will have their current data(units, maps won, etc.) saved to their profile in the database. If they go to the shop they will be able to enter the units that they would like to buy. As long as they have the space and money they will be able to buy the units they want. From their they can return to the map screen and exit the game which will close the game screen.

3. The user logs into the game with no issues. The user's previous save data is there with no issues(such as corruption). They are able to buy some new units from the shop that they have leftover from their last play. They buy some new units and return to the map menu. They choose a new battle. They are able to play out a challenging but fun scenario. They save their game and then exit satisfied.

4. The user logs into the game. Their save information was corrupted forcing them to start from the beginning. They enter a new map and do not have fun during the gameplay. They exit the game frustrated and unsatisfied.

5. Description : A series of menus will allow you to play a strategy game. You will start on the login screen that will allow you to load your progress. Followed by a map screen which will allow you to save your progress, link you to battle maps, or link you to the shop. In the shop you will be able to buy new troops for your army, as long as you have the money and the space. In the battle map you will be able to fight battles, that if won will open up more battles to fight in.
Nouns of Classes : Login class, allows the player to login or register a username. Map Class, allows the player to save their progress, link to the shop, or go to a battle map. Shop class, allows you to buy new units. Battle class, where the player will be able to fight enemies on the field of battle. Player class, keeps track of the stats of the players soldiers. Enemy class, keeps track of the stats for the enemy soldiers. Username class, keeps track of all of the players usernames, passwords, and progress.
Login class : boundary class
Map Class : boundary class
Shop Class : control class
Battle Class : control class
Player Class : entity class
Enemy Class : entity class
Username Class : entity class