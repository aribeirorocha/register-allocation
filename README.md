# 🧮 Register Allocation via Graph Coloring

![C++](https://img.shields.io/badge/C%2B%2B-00599C?logo=cplusplus&logoColor=white) ![Make](https://img.shields.io/badge/Make-427819?logo=gnu&logoColor=white) ![Grade](https://img.shields.io/badge/Grade-19%2F20-brightgreen)

Tackles a classic **compiler** problem: given the live ranges of a program's variables and **K** available CPU registers, assign registers so that variables that are alive at the same time never share one.

> Project 2 for **Algorithm Design (DA)** — BSc in Informatics and Computing Engineering (L.EIC), FEUP, 2025/2026. **Final grade: 19/20.**

## 🧠 Approach
1. **Webs:** live ranges are merged into *webs*, the sets of program points where a variable is alive.
2. **Interference graph:** two webs are connected if they are alive at the same point. A definition that starts exactly where another value is last used does not count as a conflict.
3. **Graph coloring with K colors:** each color is a register.

### Algorithms implemented
| Mode | Strategy |
|---|---|
| **Basic** | Greedy simplification + coloring, O(V² + E) |
| **Spilling** | Sends up to K webs to memory when the graph cannot be colored |
| **Splitting** | Splits webs into smaller live ranges to reduce interference |
| **Free** | Our own heuristic, based on a **cost-benefit metric** |

## ✨ Other features
- Parsers for range and register files, and writers for the allocation output
- Test datasets with their ideal allocations
- Code documented with **Doxygen**, including the time complexity of every function

## ▶️ How to run
```bash
make
./myProg                                           # interactive mode
./myProg -b <ranges> <registers> <output>          # batch mode
```

## 👤 My contribution
I was the **main contributor**: the interference graph and webs, the `Allocator` algorithms (including the custom heuristic), the parser and output writer, and the Doxygen documentation.

## 👥 Team
André Rocha and two colleagues (group T06_G)
