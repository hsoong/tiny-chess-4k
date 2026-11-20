# tiny-chess-engine-4k

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01)

An alpha-beta chess engine in 4,096 bytes of Python, entered in make.fun's
tiny-chess-01 bounty: it plays the house gauntlet through the env at
MAKEFUN_ENV_URL, searching under a fixed node budget so every move is
reproducible.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 main.py
```

The readable source is `chess_source.py`; `main.py` is that source packed by
`makefun compress`.

## How it searches

Alpha-beta with iterative deepening, a transposition table, null-move pruning,
late-move reductions, killer and history ordering, and a quiescence search over
captures and promotions. Every move comes from a fixed node budget, never a
clock, so a trial replays move for move.
