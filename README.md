# Sudoku Solver: IDA* + MRV vs DFS + MRV

Solutions for LeetCode #37 (Sudoku Solver) in Python. Course project for
Algorithm Design (CSX3009), Assumption University of Thailand.

## Results (LeetCode)

| Algorithm | Runtime | Memory | Status |
|---|---|---|---|
| DFS + MRV | 870 ms | 19.31 MB | Accepted |
| IDA* + MRV | 1296 ms | 19.73 MB | Accepted |

## Key finding

In this implementation, g(n) rises by 1 as h(n) (empty cells) falls by 1,
so f(n) stays constant. The IDA* threshold never prunes, so IDA* + MRV
searches the same tree as DFS + MRV with extra cost calculations.

## Complexity

- Time: O(9^n) worst case, n = empty cells (MRV reduces branching in practice)
- Space: O(n) recursion stack

## Files

- `ida_star.py`: IDA* + MRV (Almina Nitinansakul)
- `dfs.py`: DFS + MRV (Marazal Bahrainee Islam)
- `Sudoku_Solver_Report.pdf`: full analysis

## Run locally

```
python ida_star.py < puzzle.txt
```

Each puzzle file has 9 lines of 9 space-separated cells, with `.` for empty.
