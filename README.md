<div align="center">
  <h1>Python Algorithms</h1>
  <p>A curated collection of classic algorithms and data structures implemented in Python — for learning and reference.</p>
</div>

This repository contains topic‑organized Python implementations ranging from searching, sorting, backtracking, dynamic programming, graph theory, linear algebra, machine learning, image processing, and more. Implementations prioritize clarity and education over micro‑optimizations.

Important notes:

- These implementations are educational. Prefer the Python standard library or well‑maintained third‑party libraries for production.
- Many modules include doctests and/or runnable examples.

## Requirements

- Python >= 3.14
- Optional tooling: [uv](https://docs.astral.sh/uv/) for fast dependency management, [pytest](https://docs.pytest.org/) for tests, [ruff](https://docs.astral.sh/ruff/) for lint/format, [Sphinx](https://www.sphinx-doc.org/) for docs.

## Installation

You can use this repository without installing anything (run modules directly), or set up a virtual environment and install dependencies.

Recommended with uv (uses `pyproject.toml` and `uv.lock`):

```powershell
# Create a virtual environment and install base dependencies
uv sync

# Optionally install additional groups
uv sync -g test      # test tools
uv sync -g docs      # documentation build tools
```

Alternative with pip (base dependencies only):

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -e .
```

## Quick start

Run an algorithm module directly (prints results to the console):

```powershell
python -m backtracking.n_queens
```

Import and use a function in your own code:

```python
from bit_manipulation.is_power_of_two import is_power_of_two

print(is_power_of_two(8))   # True
print(is_power_of_two(17))  # False
```

Most modules contain doctest examples. You can run them via `pytest` or directly from the module when available.

## Project structure

Top‑level topic folders (non‑exhaustive):

- `backtracking/` — N‑Queens, Sudoku, Hamiltonian cycle, and related search problems
- `bit_manipulation/` — bitwise operations, Gray code, counting bits, power‑of‑two checks
- `data_structures/` — stacks, queues, hash maps, trees, heaps
- `divide_and_conquer/`, `dynamic_programming/`, `greedy_methods/` — core algorithmic paradigms
- `graphs/`, `networking_flow/` — graph traversal, shortest paths, max flow
- `maths/`, `linear_algebra/`, `matrix/` — numerical and algebraic utilities
- `sorts/`, `searches/` — classic sorting and searching algorithms
- `computer_vision/`, `digital_image_processing/`, `audio_filters/` — signal and image processing
- `machine_learning/`, `neural_network/` — basic ML and NN examples
- `project_euler/` — Project Euler problem solutions (not covered by test coverage)

Explore each folder’s `README.md` where present for more details.

## Testing

This project uses `pytest` and doctests.

```powershell
uv run pytest -q             # with uv
# or
pytest -q                    # if installed in your environment
```

## Code style

This repository is configured for `ruff` (format + lint). Suggested workflow:

```powershell
uv run ruff format .
uv run ruff check .
```

The configuration lives in `pyproject.toml` and targets Python 3.14.

## Documentation

Sphinx configuration is provided. To build HTML docs locally:

```powershell
uv sync -g docs
uv run sphinx-build -b html docs docs/_build/html
```

Open `docs/_build/html/index.html` in a browser.

## Contributing

Contributions are welcome. Keep implementations simple, readable, and well‑documented. Prefer type hints and include doctests where practical. Please run ruff and tests before opening a PR.

## License

MIT — see `LICENSE.md`.

## Acknowledgments

This codebase is inspired by and derived from the open‑source efforts of the TheAlgorithms community. Thanks to all contributors for educational implementations and ideas.
