# Tic-Tac-Toe-RL-Project

This repository contains a Python implementation of a Tic Tac Toe game with an AI opponent. The AI opponent is implemented using the value iteration algorithm to find the optimal policy for each state of the game.

## Requirements

- Python 3.x
- NumPy library

## Usage

1. Clone the repository:
   git clone <repository_url>

2. Change to the project directory:
   cd tic-tac-toe-ai

3. Run the game:
   python tic_tac_toe.py

   The game will start, and the board will be displayed. The player (represented by '2') will play against the AI opponent (represented by '1'). The game will continue until a player wins, there is a draw, or you interrupt the program.

## How it works

The AI opponent uses the value iteration algorithm to find the optimal policy for each state of the game. It computes the transition probabilities, rewards, and value function for each possible action. The optimal policy selects the action that maximizes the value function at each state.

The implementation includes the following components:

- `board`: Represents the Tic Tac Toe game board.
- `actions`: List of possible actions (empty spaces) on the board.
- `check_win(board, player)`: Function to check if a player has won.
- `T`: Probability transition function that calculates the transition probabilities between states.
- `policy`: Arbitrary policy that randomly selects an action from available actions.
- `W`: Value function representing the expected rewards for each action in each state.
- `gamma`: Discount factor for future rewards in the value iteration algorithm.
- `opt_policy`: Optimal policy that selects the action that maximizes the value function at each state.

The example game simulation demonstrates the usage of the optimal policy to play against the AI opponent. The game will continue until a player wins, there is a draw, or there are no more actions available.

## Contributions

Contributions to this repository are welcome. If you have any suggestions, bug fixes, or additional features, feel free to submit a pull request.

## Explaination

The provided code is a Python implementation of a Tic Tac Toe game with an AI opponent. It uses the value iteration algorithm to find the optimal policy for each state of the game.

The code begins by importing the necessary libraries, namely `numpy` for numerical operations and `random` for generating random values.

Next, a Tic Tac Toe game board is created using a NumPy array of zeros with a shape of 3x3. Each element of the array represents a cell on the game board.

A list called `actions` is created to store all the possible actions (empty spaces) on the game board. It is initialized with tuples representing the row and column indices of each cell on the board.

The `check_win` function is defined to check if a player has won the game. It takes the game board and the player's number as input and checks for winning conditions in rows, columns, and diagonals.

A 3D NumPy array called `T` is created to represent the probability transition function. It stores the transition probabilities between states based on the current and next actions. It is initialized with zeros.

The code then iterates over each action and next action in the `actions` list. For each pair of actions, it checks if they are valid moves (neither the current nor the next space is already occupied). If they are valid, it calculates the transition probabilities based on whether it's the opponent's turn (player 1) or the player's turn (player 2). It also checks if a player has won after each move to invalidate further moves if necessary.

An arbitrary policy is created by randomly selecting an action from the available actions for each state of the game. This policy is stored in the `policy` list.

The value iteration algorithm is implemented next. The code initializes the discount factor `gamma` and creates an array `W` to represent the value function. It then iterates for a fixed number of iterations (100 in this case) or until the value function converges.

Within each iteration, the code creates a copy of the previous value function to compare convergence. Then, for each action, it calculates the expected rewards for each possible action based on the transition probabilities and the previous value function. The maximum expected reward is selected as the new value for that action. This process continues until the value function converges.

Once the value iteration algorithm is complete, the code creates an optimal policy by selecting the action that maximizes the value function for each state. The optimal policy is stored in the `opt_policy` list.

Finally, an example game simulation is provided using the optimal policy. The code displays the current game board and checks for a win, a draw, or continues the game. The opponent (player 1) randomly selects an action, and the player (player 2) selects the action based on the optimal policy. This process continues until the game reaches a win, a draw, or there are no more actions available.

Overall, the code demonstrates how to implement a Tic Tac Toe game with an AI opponent using the value iteration algorithm to determine the optimal moves for the AI player.
