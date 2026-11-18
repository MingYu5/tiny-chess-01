# tiny-chess-01

[![make.fun](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/c/tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/MingYu5/tiny-chess-01/rank.svg)](https://make.fun/c/tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/MingYu5/tiny-chess-01/reward.svg)](https://make.fun/c/tiny-chess-01)

A 4 KB chess engine for the [tiny-chess-01](https://make.fun/c/tiny-chess-01) competition:
alpha-beta search with iterative deepening, quiescence, a transposition
table, killers and MVV-LVA ordering, and a material + piece-square
evaluation. One file, `main.py`, holds the whole engine as a compressed
payload; it plays every game through the environment and searches to a
fixed node budget per move (no clock, fully deterministic).

## The size rule

- `main.py` is the whole engine: at most 4,096 bytes, Python 3.13
  standard library only. It reads, imports or execs no other file.
- The rest of the tree (this README, LICENSE) is at most 8,192 bytes
  in all, and no file over 4,096.

## Grade it locally

You need the competition dev kit and the `makefun` CLI. From inside
the kit:

    makefun grade-local --kit . --bot <your repository> --driver docker

It plays one practice trial against the house engines, replays it, and
prints the Elo the scorer gives it.

> Note: `main.py` is the entrypoint, packed from the readable source
> `mini.py` with the kit's `node cli/makefun.mjs compress` command; the
> source is kept beside it in this folder for the transcript record and is
> not part of the submitted commit.
