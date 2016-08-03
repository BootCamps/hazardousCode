Hazardous vs. Clean Code

Objective: Demonstrate the different 'feel' of added features to a hazardous code base versus adding the same features to a clean code base.

Concepts:
	Testing safety net
	Limits of manual testing
	Tightly coupled code
	Large methods
	Deep nesting
	Cryptic variable names
	
Signals:
	Using debugger to figure out how it works
	Making changes and waiting on long running tests
	One change unexpected breaks other things
	No feel for how close to getting done

Exercise:
	Learning group breaks into pair
	Half the pairs drive new features in the Game A code
	Half the pairs drive new features in the Game B code (src)
	Discuss joys and pains of each code base
	Pairs swap and repeat the exercise



A Tale of Two Codebases: Two Versions of 10 x 10 TicTacToe Game where First Player to 5-in-a-row Wins

What you'll need for this series of exercises:

-- Eclipse 3.2+

Detailed Instructions:

This Eclipse project consists of two different implementations of the same 10 x 10, first-to-5 TicTacToe game: an older, 
legacy version, and a newer, mostly-test-driven replacement. Below we ask you to compare and learn about the two games, and to make some specific changes to the newer one. 

-----------

The older game version consists of a single large class in its own source folder and package: legacy/legacyGame.LegacyGame. 
The newer game version consists of the src/controller.gameplay.TicTacToeGame class, and several other classes 
(in various packages).

Right-click on the GameGUI applet in the package view.applet, to play the newer TicTacToeGame and get a feel for it. (You are X's, and the computer is O's.)
The LegacyGame has its own applet in the legacyCode package, and you can run and look at the code.

Look carefully at the LegacyGame class (in package legacy/legacyGame), and compare it to the new TicTacToeGame and its various classes (in packages src/model.gamestate, 
src/model.patterns, and src/model.patternsearching). After comparing the old game and the new, write down some of the DESIGN DIFFERENCES between them. 

 -- Can you tell any differences in overall game play strategy between the two games?
 -- Can you mostly tell what is going on in the new game?
 -- Can you mostly tell what is going on in the old game?
 -- What do you like most and least about the old game design?
 -- What do you like most and least about the new game design?
 
You can learn more about the new game by looking at and running the unit tests in the test source folder. 
 -- What do the unit tests tell you about the new game?
 -- What do you like and not like about any of these TestCases and test methods? 
 
 You can run the old game against the new game using the single test method in the OldGameAgainstNewGameTests TestCase in gameComparison.harness.twogame.OldGameAgainstNewGame. 
 This test method is currently set to play the two games against each other 500 times. 
  -- What does running this TestCase tell you about the old and new games? 
  
Exercise One: Twenty Minutes
  -- In the tested TicTacToeGame, what would it take to enable the human player to win if they get 5 in a row, while the computer must get 6 in a row?   
  -- Spend no more than about 45 minutes trying to test-drive this change, ensuring that all tests keep running green. 
  -- Use the tests as your guide to how and where to change the code. 
  -- Then attempt to verify your change manually by running the applet. 
  
Exercise Twenty Minutes
  -- In the old legacyGame TicTacToeGame, what would it take to enable the human player to continue to win if they get 5 in a row, while the computer must now get 6 in a row to win?   
  -- Spend no more than about 20 minutes trying to hack this into place, retrofitting junit tests, and then verifying manually with the applet. 
