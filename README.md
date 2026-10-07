# BFS vs DFS Route Finder

**Course:** 02AML204 – Introduction to Artificial Intelligence
**Name:** Soham Nanaso Patil | **PRN:** 25UAM124 | **Division:** B

A small Python project that finds a route in an unweighted graph using
Breadth-First Search (BFS) or Depth-First Search (DFS) and compares the two
by execution time, nodes expanded and path length.

## Project Parts

| SLE | Work | Deliverable |
|-----|------|-------------|
| SLE-1 | Search agent code | Source code, README, contribution log |
| SLE-2 | Profiling BFS vs DFS | Profiling report (docx) |
| SLE-3 | Architecture using the full C4 model | SLE3_25UAM124_SohamPatil.docx |

## Features

- BFS (queue-based) and DFS (stack-based) on the same graph and neighbour order
- Returns the path, path length and nodes expanded
- Measures mean execution time using `time.perf_counter_ns()` (5,000 runs)
- Tested on 5-node, 10-node and 16-node graphs

## Project Structure

```
.
├── [search.py]              # bfs(), dfs(), reconstruct_path()
├── [profile.py]             # timing and node counting
├── README.md
├── contribution_log.md
└── reports/
    ├── SLE2_25UAM124_BFS_vs_DFS_Corrected.docx
    └── SLE3_25UAM124_SohamPatil.docx
```

## How to Run

```bash
git clone https://github.com/SohamP27/[repo-name].git
cd [repo-name]
python [main_file].py
```

Requires Python 3.8+. No external libraries needed.

## Results (from SLE-2)

| Case | Algorithm | Avg Time (µs) | Nodes Expanded | Path Length |
|------|-----------|---------------|----------------|-------------|
| Best (5 nodes) | BFS | 0.837 | 2 | 1 |
| Best (5 nodes) | DFS | 0.754 | 2 | 1 |
| Average (10 nodes) | BFS | 2.274 | 10 | 4 |
| Average (10 nodes) | DFS | 1.637 | 5 | 4 |
| Worst (16 nodes) | BFS | 3.657 | 16 | 4 |
| Worst (16 nodes) | DFS | 4.577 | 15 | 14 |

**Conclusion:** Both have O(V + E) time complexity. BFS guarantees the shortest
path in an unweighted graph. DFS can be faster when branch order is lucky, but it
returned a 14-edge route where BFS found a 4-edge route.

## Architecture (C4 Model, SLE-3)

- **Context:** User → BFS/DFS Route Finder → Path + Metrics
- **Containers:** Input Module, Search Engine, Visited Set, Profiler, Output Module
- **Components (Search Engine):** Frontier, Neighbour Expander, Explored Set, Goal Test, Path Reconstructor
- **Code:** `Graph`, `bfs()`, `dfs()`, `reconstruct_path()`, `profile()`, `main()`

See the full report in `reports/`.

## AI Usage

AI tools were used for support. See [contribution_log.md](contribution_log.md) for details.

## Author

Soham Nanaso Patil – [GitHub](https://github.com/SohamP27)
