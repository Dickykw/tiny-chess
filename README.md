# tiny-chess-01

A 4KB Python chess engine. 0x88 board, negamax + alpha-beta, quiescence search, transposition table, killer moves, MVV-LVA ordering, fixed node budget (iterative deepening). Deterministic, no clock, stdlib only.

`main.py` is a zlib+base85 packed build of the engine source (packing is allowed by the rules; the unpacked source is the engine).

## Build

The packed `main.py` decompresses to the engine source. To rebuild from the readable source, compress it with `zlib.compress(src, 9)` and base85-encode it into the loader.

## Play

The engine speaks the make.fun env HTTP protocol (`MAKEFUN_ENV_URL`): `POST /game`, `POST /move`, `POST /resign`. It plays UCI moves.
