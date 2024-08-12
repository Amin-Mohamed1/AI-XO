# Minimax Algorithm for Tic Tac Toe

![image](https://github.com/user-attachments/assets/42802bc4-d0c5-42ec-a0ec-0c0273b59cd5)

The Minimax algorithm is a decision-making algorithm used in two-player turn-based games such as Tic Tac Toe. It is designed to find the optimal move for a player, assuming that the opponent is also playing optimally. The algorithm works by recursively exploring all possible moves and their outcomes to determine the best possible action.

## Key Components of Minimax Algorithm

1. **Game State Representation**:
   - The game board is represented as a 3x3 grid with three possible values: `X`, `O`, and `EMPTY`.
   - `X` and `O` are the two players, while `EMPTY` denotes an empty cell on the board.

2. **Player Function**:
   - Determines whose turn it is to play by counting the number of `X` and `O` on the board.
   - If they are equal, it is `X`'s turn; otherwise, it is `O`'s turn.

3. **Actions Function**:
   - Generates all possible moves that can be made from the current board state.
   - Returns a set of coordinates for empty cells.

4. **Result Function**:
   - Simulates the board state after a specific move is made.
   - Returns a new board with the move applied.

5. **Winner Function**:
   - Checks if there is a winner by examining rows, columns, and diagonals.
   - Returns the winner (`X` or `O`) if there is one, or `None` if there isn't.

6. **Terminal Function**:
   - Determines if the game is over, either because of a win or a draw.
   - Returns `True` if the game is over and `False` otherwise.

7. **Utility Function**:
   - Assigns a numerical value to a terminal state: `1` if `X` wins, `-1` if `O` wins, and `0` for a draw.

8. **Minimax Function**:
   - The core of the algorithm that recursively explores all possible game states to find the optimal move.
   - It uses two helper functions, `max_value` and `min_value`, to simulate the best possible move for the current player and the opponent respectively.

## Minimax Process

- **Max Value**:
  - Called when it is `X`'s turn (the maximizing player).
  - Evaluates all possible moves, recursively calling `min_value` for each resulting board state.
  - Returns the maximum value and corresponding move, ensuring `X` makes the best possible move to maximize its chances of winning.

- **Min Value**:
  - Called when it is `O`'s turn (the minimizing player).
  - Evaluates all possible moves, recursively calling `max_value` for each resulting board state.
  - Returns the minimum value and corresponding move, ensuring `O` makes the best possible move to minimize `X`'s chances of winning.

## Example Walkthrough

1. **Initial Call**:
   - `minimax` is called with the current board state.

2. **Determining Player**:
   - The `player` function identifies whose turn it is.

3. **Exploring Moves**:
   - The algorithm recursively explores all possible moves using the `actions` and `result` functions.

4. **Evaluating Terminal States**:
   - At each terminal state, the `utility` function assigns a value based on the game's outcome.

5. **Recursive Backtracking**:
   - The algorithm backtracks, updating values through `max_value` and `min_value` calls to propagate the optimal move up the recursion tree.

6. **Optimal Move**:
   - `minimax` finally returns the best move for the current player based on the evaluated game tree.

## Conclusion

The Minimax algorithm ensures that both players make the best possible moves, leading to an optimal game strategy. This makes it a powerful tool in turn-based games like Tic Tac Toe, where both players aim to outsmart each other. By exploring all possible future moves and their outcomes, the algorithm can predict the best course of action, providing a clear advantage in gameplay.
