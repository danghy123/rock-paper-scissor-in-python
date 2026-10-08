# Rock Paper Scissor in Python
This is an emulation of Rock, Paper, Scissor game against a computer. I developed this small side project to keep myself sharp with using Python. The code can be rerun so the user can have a new game. This was made in Jupyter Notebook.

## Library Used
- `random`

## The Process
This section is dedicated to showcasing my thought process during the development of this mini project as well as explaining my code.
First, I wrote out various comments that give a rough framework on how I would write my code. Stuff like `# Computer chooses rock, paper, or scissor` and `# Ask: choose r, p, or s` gives me a good idea on what is suppose to be written here.
As for the actual coding, I started off by importing the Python library `random`. This library is instrumental for letting the algorithm randomly pick between rock, paper, or scissor. I defined this step with the following code:

`# Computer chooses rock, paper, or scissor`\
`choices = ['r', 'p', 's']`\
`answer = random.choice(choices)`

"r" represents Rock, "p" represents Paper, and "s" represents Scissor within the array variable "choices." Then, using the *choice()* method from the `random` library, one of the choices will get picked and stored within the variable "answer."

Next step in the coding is writing out how a user would interact with the algorithm. Following the format of the variable "choices," I define the input variable as such:

`guess = input('Rock, paper, or scissors? (r/p/s): ').lower()`\
(The method *lower()* was added in case the user accidentally has Caps Lock on when typing their guess.)

The answer of both the computer and the user would then be printed out for the latter to see after they entered their guess into the input.

Now for the most extensive part: the various outcomes this minigame could have. My thought process for this part begins with figuring out what possible outcomes could result from this game; a brief brainstorm later, I realized four possible results: winning, losing, a draw, and an invalid answer.
I chartered them up into separate sections and defined them with if-statements. Since the user inputting an invalid answer is not an intended outcome for the game, the outcome belongs in its own if-statement, separate from the other three outcomes who belong in the same if-statement together. 

`# If guess is not valid, print an error`\
    `if guess not in choices:`\
        `print('Invalid choice!')`
        
  `# Outcomes:`\
   `# If guess and answer matches, tie`\
    `if guess == answer:`\
        `print('Tie!')`

  `# These are the winning outcomes`\
    `elif ((guess == 'r' and answer == 's') or`\ 
    `(guess == 'p' and answer == 'r') or (guess == 's' and answer == 'p')):`\
        `print('You win!')`

   `# The losing outcomes are outcomes that aren't in the winning outcomes`\
    `else:`\
        `print('You lose!')`

For the finishing touch of this project, I designed a "continuation" state so that the user can see the other outcomes of this game. My thought process behind this step is first figuring out how to make game not end after the user inputs their guess.
I reframed this problem as finding a way to make the game "repeatable" and realized that I could just set what I have coded so far into a *while* loop. Of course, not everyone is gonna want to continue playing the game after their guess so I set up another input variable to allow the user to choose directly.

`# Asking the player if they want to try again`\
    `should_continue = input('Continue? (y/n): ').lower()`\
    `if should_continue == 'n':`\
        `break`

## How To Play
1. Download the file and open it up using whichever application you use for Python.
2. Select the cell box and run it (either by manually selecting the option to run it or by using the hotkey SHIFT + ENTER).
3. Make your guess within the input section.
4. Decide if you want to continue playing or not.
5. If you ever want to have another session of RPS, just re-run the cell box like in Step 2.
