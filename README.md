# THE MENACE
# Tic-Tac-Toe

## AIM 
The aim of the project is to implement menace without matchboxes and by using hash table instead. The keys in the hash-table represents each type of the match boxes which is also the different states of the board.

## INTRODUCTION
Tic-tac-toe, also known as nougats and crosses or Xs and Os, is a two-person paper and pencil game in which each player alternates marking squares in a three-by-three grid with an X or an O. The winner is the player who successfully places three of their markers in a horizontal, vertical, or diagonal row. It's a solved game with a forced draw if both players play their best.

Donald Michie created MENACE (Machine Educable Nougats And Crosses Engine) in 1961, a machine that could learn to play Nougats and Crosses better. MENACE was made from 304 matchboxes because computers were not readily available at the time.
MENACE starts with four beads of each color in the first move box, three beads in the third move box, two beads in the fifth move box, and one bead in the final move box. When a bead is removed from each box after a loss, it signifies that subsequent movements are more strongly discouraged. This allows MENACE to learn faster because the latter moves are more likely to have resulted in a loss.

## APPROACH
The approach we took in this project is first to train the menace. 
During the training, we train the menace by playing a large set of rounds. 
-	The first player “X” is random bot which picks its moves randomly from the list of available moves.
-	The second player “O” our menace bot plays the move using the minimax algorithm. 
-	We are use 4 hash tables, one for every move which keeps all the possible states as key.
-	As the simulation runs, we give certain reward and penalty for each round the menace wins or loses. If the match draws, we neither reward nor penalize the menace. 
-	After we train the bot for 500 rounds, our 4 hash tables store the keys which represent the moves taken and their score value.
The beads used to reward or punish the Menace are:
<br>
● Alpha = 0
<br>
● Beta = +1
<br>
● Gamma = -1 
<br>
● Delta = +0.5

After this training, our menace is ready to be challenged. You can play with the menace after. The menace in this case, chooses its step based on hash table values, identifies which step to take.

## PROGRAM
Below are the program details - 
###DATA STRUCTURES
We are using the following data structures for the purpose – 
-	Hash Tables – We are using hash tables to store the state of board and their score against the training rounds. 
-	2D Char Array  - We are using a 2D array to store the state of the game while training as well as playing the game.
### CLASSES
We have the following classes and methods in our project – 

### App.java
•	addButtons: Adding and enabling buttons to play TicTacToe.
•	restartTheGame: Reinitializing the button panel after every training       iteration.
•	configureLayout: initializing GUI components in a constructor.
•	recolor: Redrawing TicTacToe after every move.
•	allActionListener: Function for ActionEvent on a click.
•	startGame: Initializing board for player mode
•	simulationFunction: Training menace against the random move.
•	actionPerformed: Capturing player move and incrementing move
•	playTurn: Marking player move on Board and checking if player wins.
•	useHashMap: Selecting maxNode move from trained HashMap.
•	giveScore: Scoring previous moves based on the outcome of game.
•	calculateTotals: Calculating total wins, loses and draws during simulation.
•	returnState: Returning next state from Hash Table based on current state.

### Minimax.java
-	Minimax: Constructor of class; Initializing class variables.
-	Utility: Checking winner in the next move.
-	max_node: Returning move to maximize the value at that node.
-	min_node: Returning move to minimize the value at that node.


### Board.java
-	Board: Constructor of class; Initializing class variables.
-	printBoard: Printing the current state of Board.
-	setPlayer: Setting player for next move.
-	Move: Marking move on the TicTacToe board.
-	checkWinner: Checking winner by checking conditions on the Board.
-	printWinner: Printing the winner of the current state.
-	copyThis: Returning the copy of the current state.

## ALGORITHM

Below is the algorithm to train the menace and store it steps in hash table - 

//List of available moves
availableMove = list of available moves {0 to 8}

//4 Maps to store values for each step
HashTable <String, Integer>  mov1Map  //For step 1 of menace
HashTable <String, Integer>  mov2Map  //For step 2 of menace
HashTable <String, Integer>  mov3Map  //For step 3 of menace
HashTable <String, Integer>  mov4Map  //For step 4 of menace

For loop to train the menace
For i = 0 to 500:
	move= 0
Map<Integer, String> boardStepMap;
	While (!game.finished)
//Move 1 – Play move by random bot
		moveRandomMenace();
		availableMove.remove();
printBoard();
		if(game.finished)
			game.winner = “X won”
//Move 2 – Play move by minimax bot 
moveAIMinimax();
		availableMove.remove();
printBoard();
if(game.finished)
			game.winner = “O won”
		boardStepMap.put(move;boardState);
		move++

//Update the four maps with alpha, beta and delta values for each step 
	k in boardStepMap map
for k = 1, update mov1Map
for k = 2, update mov2Map
for k = 3, update mov3Map
for k = 4, update mov4Map
		if menace won, add or update mov[k]map with +1,
		if lost, add or update mov[k]map with -1
		if draw, no update

	print(total count);
	print(win count);
	print(loose count);
	print(draw count);


## INVARIANTS
•	Menace plays second. It always moves after the random bot or human moves.
•	Menace cannot play more than four states in a game.
•	Rewarding and punishing the menace with +1 in case of winning and losing.

## FLOW CHARTS
Here below is the flow chart for our application- 

 

OBSERVATIONS AND GRAPHICAL ANALYSIS
From the below observations we can see that the menace got trained almost at the same rate every time with different executions – 

 
 

RESULTS AND MATHEMATICAL ANALYSIS

From the above graph , It is clear that Menace is trying to learn gradually against the ransom bot. 
It can be proved mathematically  

 

## TESTCASES
We have three classes for test coverage–

AppTest.java

  

BoardTest.java

 

MinimaxTest.java

 
 
## OUTPUT SCREENS

Training Output 

![alt](https://github.com/jayeshkhattar/Tic-Tac-Toe/blob/master/photos/Training.png)

Game Screen 

![alt](https://github.com/jayeshkhattar/Tic-Tac-Toe/blob/master/photos/instance%20of%20a%20game.png)

 

## CONCLUSION
Every game menace plays four moves or fewer than four moves. The menace's likelihood of winning or drawing improves by 5 percent for every 50,000 games. The proportion of games that finish in a tie was 36 percent, whereas the number of games in which the menace wins increase dramatically as the number of trainings increases. This is because the menace becomes increasingly intelligent after many trainings, resulting in the player winning less.

## REFERENCES
<br>
Min Max
<br>

•	https://www.geeksforgeeks.org/minimax-algorithm-in-game-theory-set-1-introduction/#:~:text=Minimax%20is%20a%20kind%20of,%2C%20Mancala%2C%20Chess%2C%20etc.
<br>
•	https://en.wikipedia.org/wiki/Burnside%27s_lemma
<br>
•	https://en.wikipedia.org/wiki/Symmetry_group
<br>
Menace
<br>
•	https://www.mscroggs.co.uk/blog/tags/menace
<br>
•	https://en.wikipedia.org/wiki/Matchbox_Educable_Noughts_and_Crosses_E
<br>
•	https://www.mscroggs.co.uk/menace/
<br>
