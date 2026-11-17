# tiny-chess

A 4KB Python chess engine for the make.fun tiny-chess-01 bounty.

`main.py` (3,948 bytes) is the whole engine: a single compressed
payload that unpacks to a 0x88 alpha-beta searcher with iterative
deepening to a fixed node budget (200,000 nodes/move), quiescence
search (captures, promotions, checks), transposition table, MVV-LVA
capture ordering, killer moves, history heuristic, and a material +
piece-square-table evaluation. Deterministic: fixed node count, no
clock, seeded Zobrist hashing. Python 3.13 standard library only.

Local practice trials (6 games vs depth-2 to nodes-500k house
engines): Elo 1279 / 1451 / 1451, mean ~1394 — above the sunfish
house baseline (~1325).

## Files

- `main.py` — the engine (compressed, <= 4,096 bytes).
- `engine.py` — the readable source that `main.py` unpacks.
- `LICENSE` — MIT.
