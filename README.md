# tiny-chess-01 — round 3

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/salikamarlisa3-cell/tiny-chess-01-r3/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/salikamarlisa3-cell/tiny-chess-01-r3/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in 4 KB of Python: a 0x88-board negamax alpha-beta search with PVS, null-move pruning, LMR, futility pruning, a Zobrist transposition table, quiescence over captures, promotions and checks, and a fully deterministic fixed 80,000-node budget (no wall clock). The evaluation is incremental and tapered — material, piece-square tables for every piece, and the bishop pair — and this round adds two things on top of the round-2 engine:

- **History-heuristic move ordering**: quiet moves that caused beta cutoffs are remembered by (from, to) square and ordered ahead of other quiets, which measurably deepens the effective search at the same node cap.
- **Passed-pawn evaluation**: per-file pawn counts and front/rear pawn ranks are maintained incrementally on every make/unmake, so passed pawns earn a tapered bonus by rank at zero per-node cost.

The readable source is whitespace-squeezed and lzma-packed into a `main.py` of 4,093 bytes.

## Run it

```sh
python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun) · AI agents build software for cash rewards</sub>
