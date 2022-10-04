# OOP board game in Java using Swing

## Description
This project was created as a part of “*Object Oriented Programming Bascis*” classes on Gdańsk University of Technology. A board game was implemented using Java programming language and Swing library to create the game interface.

## The goal of the project 
The goal of this project was to implement a board game meeting some requirements stated by the supervisor. I have learnt what the OOP Paradigms are and how to recognize them. It is my first project using the Swing library, which I found quite enjoyable in creating the game interface. 

## Requirements of the project
### The aim and game structure
The aim of the project is to **implement a virtual world simulator**, which has a **two-dimensional grid structure** of any NxM size set by the user.
### Organisms
In this world there will be **simple forms of life with different behaviors**. Each of the organisms occupies exactly one field in the array, on each field there can be at most one organism (in the event of a collision, one of them should be removed or moved).
### Turns and behaviour
The simulator is to be turn-based. In each turn, all organisms existing in the world are to perform an action appropriate to their type. Some of them will move (animal organisms), some will be stationary (plant organisms). In the event of a collision (one of the organisms will be in the same field as the other), one of the organisms wins, killing (e.g. a wolf) or driving away (e.g. a turtle) a competitor. The order of movements of organisms in a turn depends on their initiative. The animals with the highest initiative move first. In the case of animals with the same initiative, the order is determined by the principle of seniority (the first moves longer living). Victory at the meeting depends on the strength of the body, although there will be exceptions to this rule. With equal strength, the organism that attacked wins.
### The human species 
A specific type of animal is to be the Human. Unlike animals, humans do not move randomly. The direction of its movement is determined before the start of the turn using the arrow keys on the keyboard. Man also has a special skill which can be activated with a separate button. The activated skill remains active for 5 consecutive turns, after which it is deactivated. After deactivation, the skill cannot be activated until 5 consecutive turns have passed.

### Display information about the current game state
When starting the program, several pieces of all types of animals and plants should appear on the board. The program window should contain a field in which information about the results of fighting, plant consumption and other events occurring in the world will be written.

## Object Oriented Programming Paradigms	
The project was implemented in Java, fulfilling all the object-oriented paradigms:
 1. **Abstraction**: Each organism in the game serves as a model for an abstract "performer" that can perform its own action and communicate with other organisms in the game without revealing how the trait is implemented.
 2. **Encapsulation**: fields in classes responsible for storing information about a given state are private fields, so that other organisms do not have direct access to variables. Other organisms can influence a given field only through the "set" function, but thanks to "getter" they can obtain information about a given value.
 3. **Inheritance**: an object hierarchy is created in the project. The Organism, Plant, TrujacaRoslina and Animal classes are abstract classes. Successive classes inherit from each other, thanks to which the given properties and functionalities are transferred or modified, if necessary.
 4. **Polymorphism**: the project uses classes (Organism, Animal, Plant, TrujacaRoslina) and abstract methods (Action in Organism method). How the method is invoked for a given object depends on the dynamic type, not the static type. A method with the same name may have a different effect on an object depending on the class of that object.

## Accomplished tasks – implementing the game
-	Implementation of the gray world and its visualization.
-	Implementation of all mandatory animal species.
-	Implementation of all plant species.
-	Implementation of the Man moved by the arrows on the keyboard.
-	Implementation of human skills.
-	Implementation of the ability to save to file and load from the state of the virtual world.
-	Implementation of the possibility of adding organisms to the game world. In all fields it is impossible to add with corrections in the world.
-	Implementation of an abstract for the world with two implementations. In one implementation, a game on a grate, in the other, a game on a board divided into cubic fields (as in a hex board game).

## Description of how it works
After starting the program, select whether a new world will be created or the world will be loaded from a txt file.
The methods in the World class are responsible for the course of the game. The game board is a two-dimensional board. The Swing library is used to visualize the board.
When the world is made, a certain proportion of all halves of the world is filled. With the help of an array of variable sizes (ArrayList) and the shuffle method, the organisms are placed randomly on the board's fields.
The execution of the next turn is initiated by the buttons next to the board. The World class includes the TakeTurn function responsible for the turn-based course of the game. Before the next turn is performed, the list is updated and sorted with all organisms that have not yet moved. During each turn, the console displays information about the initiative, age, and position of the organisms that perform their actions. Moreover, information about the course of collisions between organisms is also printed. When the turn is over, the current board is displayed thanks to the Swing library.
The man is controlled with the arrow keys.
Using the buttons next to the board, it is possible to save the world to a txt file, activate a special skill and quit the game.

## Sample screenshots from the game
### Main menu:
![obraz](https://user-images.githubusercontent.com/72522808/193759502-b1c585ba-7137-4325-a619-d800b41ab445.png)


### Read the game state from *.txt file:
![obraz](https://user-images.githubusercontent.com/72522808/193759554-26e9ef99-917a-4e85-b5be-5f3b01891415.png)


### Creating new game:
![obraz](https://user-images.githubusercontent.com/72522808/193759576-f8b08b52-fa50-4145-8a8c-e826e359476c.png)

### Sqaure fields:
![obraz](https://user-images.githubusercontent.com/72522808/193759597-8293f4d2-8256-4483-bbb0-e98f798b59b7.png)

### Hex fields:
![obraz](https://user-images.githubusercontent.com/72522808/193759621-ec3053be-cc5b-4e9b-b695-4e7841f2d49e.png)

### Each free field has a menu to add an organism on it:
![obraz](https://user-images.githubusercontent.com/72522808/193759669-e7741039-6e79-436d-bf7d-5468a5a76b48.png)

### Saving the game state to *.txt file:
![obraz](https://user-images.githubusercontent.com/72522808/193759712-748bae32-af42-4d37-bf73-98a63e405fdb.png)



