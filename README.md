# SAT Solvers — Algorithm Comparison

A Python implementation and benchmark comparison of 4 classical SAT solving algorithms on CNF formulas in DIMACS format.

## Algorithms Implemented

| Solver | File | Description |
|---|---|---|
| Resolution | `resolution.py` | Iterative clause resolution until empty clause or fixpoint |
| DP | `dp.py` | Davis–Putnam: unit propagation + pure literal elimination + resolution |
| DPLL | `dpll.py` | Davis–Putnam–Logemann–Loveland: recursive backtracking with unit propagation |
| CDCL | `cdcl.py` | Conflict-Driven Clause Learning: DPLL + conflict analysis + clause learning |

## Structure
├── parser.py          # DIMACS CNF file parser
├── resolution.py      # Resolution solver
├── dp.py              # DP solver
├── dpll.py            # DPLL solver
├── cdcl.py            # CDCL solver
├── run_all.py         # Benchmark runner (outputs results.txt)
└── benchmarks/
  ├── uf20-91/       # SAT instances (20 variables, 91 clauses)
  └── uuf50-218/     # UNSAT instances (50 variables, 218 clauses)

## Running

```bash
python run_all.py
```

Results are saved to `results.txt`. Each solver is timed in milliseconds per instance.

## Benchmarks

Uses standard SATLIB benchmark sets in DIMACS CNF format:
- `uf20-91` — satisfiable instances (20 vars, 91 clauses)
- `uuf50-218` — unsatisfiable instances (50 vars, 218 clauses)

Resolution is skipped for instances with more than 40 clauses due to clause explosion.

## Stack

Python 3
