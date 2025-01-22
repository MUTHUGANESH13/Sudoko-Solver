# Sudoku Solver

## Overview
The Sudoku Solver is a C program that provides an interactive platform to solve Sudoku puzzles of varying sizes. It includes functionality to reset the board, input numbers, and solve or unsolve Sudoku problems. The program supports board sizes of up to 36x36.

---

## Features

- **Interactive Command-Based Interface**: Allows users to input commands to modify and solve the Sudoku puzzle.
- **Flexible Board Sizes**: Supports various board sizes, such as 4x4, 9x9, 16x16, 25x25, and 36x36.
- **Automatic Solver**: Solves Sudoku puzzles and handles invalid boards gracefully.
- **Error Handling**: Provides informative feedback for invalid commands or inputs.
- **Reset and Backup Functionality**: Resets the board or restores the last solved Sudoku puzzle.

---

## Commands

### General Commands:
- **`quit`**: Exits the program.
- **`help`**: Displays the help menu with available commands.

### Board Configuration:
- **`reset`**: Resets the board to its initial state (all cells empty).
- **`rows number`**: Sets the number of rows for the board. Must be a square of an integer (e.g., 4, 9, 16, 25, 36).
- **`columns number`**: Sets the number of columns for the board. Functions similarly to `rows`.

### Sudoku-Specific Commands:
- **`solve`**: Solves the entered Sudoku puzzle.
- **`unsolve`**: Restores the board to the last solved state.

### Inputting Values:
- **`row,column,value`**: Marks the specified cell with the given value. For example, `1,1,5` sets the top-left corner cell to 5.

---


## Implementation Details

- **Data Structures**:
  - `dataTables[MAX_SIZE][MAX_SIZE]`: Stores the current Sudoku board.
  - `backupBoard[MAX_SIZE][MAX_SIZE]`: Stores a backup of the most recently solved board.

- **Functions**:
  - `reset_board()`: Resets the board to its initial empty state.
  - `handle_command(char* command)`: Processes user input and executes the corresponding command.
  - `solved_sudoku(int board[MAX_SIZE][MAX_SIZE], int solutions)`: Recursive backtracking algorithm to solve the Sudoku puzzle.
  - `is_invalid_number(int board[MAX_SIZE][MAX_SIZE], int row, int col)`: Validates the placement of a number.
  - `print_board(int board[MAX_SIZE][MAX_SIZE])`: Displays the current board state in a formatted grid.

---


## Example Session

```text
WELCOME TO SUDOKU SOLVER
  1  2  3  4  5  6  7  8  9
 +---+---+---+---+---+---+---+---+---+
1|   |   |   |   |   |   |   |   |   |
 +---+---+---+---+---+---+---+---+---+
...

Enter your command: 1,1,5
  1  2  3  4  5  6  7  8  9
 +---+---+---+---+---+---+---+---+---+
1|  5|   |   |   |   |   |   |   |   |
 +---+---+---+---+---+---+---+---+---+
...

Enter your command: solve

1 solution(s).
  1  2  3  4  5  6  7  8  9
 +---+---+---+---+---+---+---+---+---+
1|  5|  3|  4|  6|...

Enter your command: quit
Thank you
```

