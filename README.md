# Sudoku Solver and Magic Square Puzzle Solver

## Overview

This repository contains two projects: a Sudoku solver and a Magic Square puzzle solver. The Sudoku solver uses backtracking search with various heuristics and the AC-3 algorithm for arc consistency. The Magic Square puzzle solver uses a genetic algorithm to find solutions to a 3x3 magic square puzzle.

## Sudoku Solver

The Sudoku solver solves a classic 9x9 Sudoku puzzle, where the goal is to fill in the empty cells such that every row, column, and 3x3 box contains exactly the digits 1 through 9, each occurring once.

### Features

- **Backtracking Search**: Uses backtracking to fill in the Sudoku board.
- **Heuristics**: Implements Minimum Remaining Values (MRV), Degree Heuristic, and Least Constraining Value (LCV) to optimize the search.
- **Arc Consistency (AC-3)**: Reduces the domains of the variables to make the puzzle easier to solve.

### Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/sudoku-magic-square-solver.git
   cd sudoku-magic-square-solver
   ```

2. Run the Sudoku solver:
   ```python
   python sudoku_solver.py
   ```

3. Choose the heuristic:
   - `1` for MRV
   - `2` for Degree Heuristic
   - `3` for basic backtracking

4. The program will print the solved Sudoku board and the execution time.

### Code Explanation

- **print_board(board)**: Prints the Sudoku board.
- **find_empty(board)**: Finds the next empty cell on the board.
- **is_valid(board, num, pos)**: Checks if placing `num` at `pos` is valid.
- **find_empty_with_mrv(board)**: Finds the empty cell with the fewest legal values.
- **find_empty_with_degree(board)**: Finds the empty cell with the most constraints on its neighbors.
- **least_constraining_value(board, pos)**: Orders the values by how few constraints they place on other cells.
- **solve(board, choice)**: Solves the Sudoku using the chosen heuristic.
- **enforce_arc_consistency(board)**: Ensures arc consistency using the AC-3 algorithm.
- **preprocess_with_ac3(board)**: Preprocesses the board with AC-3 before solving.

## Magic Square Puzzle Solver

The Magic Square puzzle solver solves a 3x3 magic square puzzle using a genetic algorithm. The goal is to rearrange the numbers 1 to 9 such that the sum of the numbers in each row, column, and diagonal equals 15.

### Features

- **Genetic Algorithm**: Uses a genetic algorithm to find solutions to the magic square puzzle.

### Usage

1. Run the Magic Square puzzle solver:
   ```python
   python magic_square_solver.py
   ```

2. The program will print the best magic square found and the number of generations it took to find it.

### Code Explanation

- **fitness(square)**: Calculates how close the square is to being a magic square.
- **swap_elements(square)**: Randomly swaps two elements in the square, excluding the central number.
- **Main loop**: Runs the genetic algorithm until a solution is found or the maximum number of generations is reached.

## Dependencies

- Python 3.x
- NumPy

You can install the required dependencies using:
```bash
pip install numpy
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
