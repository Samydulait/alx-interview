# 0x05 N QUEENS

# This README file is for the 0x05. N Queens project. In this folder you will fing the following files

## Project Tasks

`0. N queens`

Chess grandmaster `Judit Polgár`, the strongest female chess player of all time

The N queens puzzle is the challenge of placing N non-attacking queens on an N×N chessboard. Write a program that solves the N queens problem.

* Usage: `nqueens N`
  * If the user called the program with the wrong number of arguments, print `Usage: nqueens N`, followed by a new line, and exit with the status `1`
* where N must be an integer greater or equal to `4`
  * If N is not an integer, print `N must be a number`, followed by a new line, and exit with the status `1`
  * If N is smaller than 4, print `N must be at least 4`, followed by a new line, and exit with the status `1`
* The program should print every possible solution to the problem
  * One solution per line
  * Format: see example
  * You don’t have to print the solutions in a specific order
* You are only allowed to import the `sys` module

Read: `Queen`, `Backtracking`

```bash
julien@ubuntu:~/0x08. N Queens$ ./0-nqueens.py 4
[[0, 1], [1, 3], [2, 0], [3, 2]]
[[0, 2], [1, 0], [2, 3], [3, 1]]
julien@ubuntu:~/0x08. N Queens$ ./0-nqueens.py 6
[[0, 1], [1, 3], [2, 5], [3, 0], [4, 2], [5, 4]]
[[0, 2], [1, 5], [2, 1], [3, 4], [4, 0], [5, 3]]
[[0, 3], [1, 0], [2, 4], [3, 1], [4, 5], [5, 2]]
[[0, 4], [1, 2], [2, 0], [3, 5], [4, 3], [5, 1]]
julien@ubuntu:~/0x08. N Queens$
```

File: 0-nqueens.py

* The basic approach to solve the N Queens problem is by using backtracking. Backtracking is a systematic way to explore all possible configurations of the queens on the chessboard and find a valid solution. It involves placing queens one by one and then checking if the current configuration is valid. If it is not valid, then the program backtracks and tries another position.

Here's a step-by-step outline of the algorithm:

Start with an empty N×N chessboard.
Begin with the first row and try placing a queen in each cell of the first row one by one.
For each placement, check if it is safe (i.e., the queen is not attacking any other queen in the same row, column, or diagonal).
If the placement is safe, move to the next row and place a queen in the first safe cell of that row.
Repeat steps 3 and 4 until all N queens are placed on the board in non-attacking positions.
If there is no safe position in the current row, backtrack to the previous row and try placing the queen in the next safe cell of that row. Keep doing this until a valid solution is found or all possibilities are explored.
