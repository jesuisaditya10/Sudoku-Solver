def solve_sudoku(sudoku_matrix, row, col, num):
    for i in range(9):
        if sudoku_matrix[row][i] == num:
            return False
    
    for i in range(9):
        if sudoku_matrix[i][col] == num:
            return False

    start_row = 3 * (row // 3)
    start_col = 3 * (col // 3)
    for i in range(3):
        for j in range(3):
            if sudoku_matrix[start_row + i][start_col + j] == num:
                return False

    return True

def solve(sudoku_matrix):
    for row in range(9):
        for col in range(9):
            if sudoku_matrix[row][col] == 0:
                for num in range(1, 10):
                    if solve_sudoku(sudoku_matrix, row, col, num):
                        sudoku_matrix[row][col] = num
                        if solve(sudoku_matrix):
                            return True
                        sudoku_matrix[row][col] = 0

                return False

    return True

sudoku_matrix = [
    [0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 2, 0, 0, 0, 0, 0, 5, 0],
    [0, 0, 9, 0, 0, 0, 0, 0, 0],
    [7, 0, 0, 5, 0, 0, 0, 0, 0],
    [0, 0, 0, 9, 1, 0, 8, 0, 0],
    [8, 0, 0, 0, 0, 4, 0, 0, 0],
    [0, 0, 0, 0, 8, 0, 0, 0, 7],
    [0, 0, 7, 0, 0, 0, 0, 0, 0],
    [0, 0, 0, 0, 0, 0, 0, 4, 0]
]

if solve(sudoku_matrix):
    for row in sudoku_matrix:
        print(row)
else:
    print("No solution exists.")