## Python Developer @ Informal School of IT
### NT-PYTHON-06 | TEAM 4
#### Rules
* we're using English for:
    * every code: variable, function, class, module, package etc.
    * every branch name
    * every commit message
    * every Pull Request title
    * code review
    * ... basically everything!
* `master` branch will be the main branch of the project - the one with the latest and cleanest and best code possible. It's your job as a team member to make sure every code merged into `master` satisfies quality conditions.
* we're using the `feature-branch` concept for developing new functionality (for every new code):
    * we make sure we're branching of latest `master` version (available on GitHub)
    * create a new feature branch
        * the name should follow the `dash-case` (aka `kebab-case`)
        * all letters should be lowercase
        * don't use any special characters beside the dash (`-`)
    * develop the work needed
    * push the feature branch as often as possible
    * create a PR against `master`
        * briefly description of the functionality using the title of the PR
        * add details about the functionality: what it does, how can it be tested locally, what Python packages to install etc. in the description of the PR.
    * wait for code review
    * merge PR to `master` once you got the approval.
    
#### Base Requirements
1. Create an entry point of the project. This will be the script which is used to start the game. You should be able to run it from a terminal by simply running `python <your_script>.py`.
2. Create a main menu for the game. The user should have 2 options:
    * Start a new game
        * on selecting this option a message will be printed in the console: ***"Game started."***
    * Exit
        * on selecting this option the program will exit.
3. Create a system which allows the two players to alternatively select their option.
    * Make sure a selection is available - players cannot select an invalid option or an already selected field on the board.
    * Remember every choice of the two players and create a list of moves, e.g.: `[5, 4, 9, 7, 1, 2, 8, 3, 6]`
    * Once every option on the board is selected print a messages in the console:
        * First line: ***"Game ended."***
        * Second line: ***<the_structure_of_movements_from_previous_point>***
4. Based on the player choices from the previous step create a system to decide if the game is won by any of the player or if the game ended as a draw.
    * if the game is won by a player show the following message in the console: ***"Player 1 has won the game. Congrats!"*** (if Player 1 won the game, otherwise Player 2)
    * if the game ended as a draw should the following message:  ***"Game ended as a draw. Have another game?"***
5. Integrate the previous two functionalities and do the game status (won or draw) once an option is selected by any of the two players. Stop the game and show the final result.
6. Create a system which will allows two players to play an infinite amount of games until they end up selecting the ***Exit*** option of the main menu.

#### Further enhancements
* Create a GUI for the game using Tkinter
* Add functionality to allow players to set their names before the start of the game..
* Add functionality to allow selecting a game system:
    * add support for single game only
    * add support for 2/3 (the winner will be the one who wins 2 games out of a maximum of 3)
    * add support for 3/5 (the winner will be the one whi wins 3 games out of a maximum of 5)
* Add functionality to allow custom sign for each player:
    * the user should be able to select EXACTLY one character (validate s/he really selected a character)
    * use the lower case of the selected character, e.g. if the users choose A, use the a instead
* Add functionality to allow registration and authentication before a game:
    * use a JSON file (data/credentials.json)
    * each player should authenticate before playing a game based on an username and password
    * every player should have an account and we could keep track of their stats
    * when you start the program, the first player will be prompted to:
        * create an account (automatically consider the user authenticate afte the sign up succeed)
        * authenticate (use username and password)
    * the same thing will apply for the second player too.
    * in order to create an account, each player should complete the following:
        * first_name
        * last_name
        * username (at least 6 characters compose of lower case letters and digits only, unique within data/credentials.json)
        * password (at least 6 characters with at least one digit)* password confirmation
* Account for the following stats:
        * total single games played (account after each game)
        * total single games won (account after each game)
        * total 2 out of 3 games played (acccount after each 2/3 series)
        * total 2 out of 3 games won (account after each 2/3 series)
        * total 3 out of 5 games played (account after each 3/5 series)
        * total 3 out of 5 games won (account after each 3/5 series)
* Add unit tests for as many functions as possible.
* Add functionality to allow Player 1 to play vs computer.
    * computer is always the second player
    * computer choices are random based on available options
    * statistics vs computer won't be write to json file
    * a game vs computer won't require authentication
