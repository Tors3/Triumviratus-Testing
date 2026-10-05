# Triumviratus — testing

Match results and full game records for the chess engine
**[Triumviratus](https://github.com/Tors3/Triumviratus)**. The summary lives in the engine
repository, under [`tests/`](https://github.com/Tors3/Triumviratus/tree/main/tests); this repository
holds the raw material behind it.

## Maurizio Platino — Triumviratus 7.0 against other engines

Played and exported by **Maurizio Platino**, the project's tester.

| Date | Opponent | Triumviratus build | Games | +W =D −L | Score | Elo (Triumviratus) | Files |
|---|---|---|---:|---|---:|---:|---|
| 2026-08-14 | pawnocchio 3.0-dev-04b3b89 | 7.0 dev, 2026-08-14 | 300 | +105 =57 −138 | 44.5% | −38 ± 15 | [folder](maurizio-platino/2026-08-14_pawnocchio-3.0) |
| 2026-08-16 | PlentyChess 8.0.0 | 7.0 dev, 2026-08-14 | 300 | +89 =68 −143 | 41.0% | −63 ± 16 | [folder](maurizio-platino/2026-08-16_plentychess-8.0) |
| 2026-09-11 | Coda 0.9.4 | 7.0, 2026-09-10 | 300 | +104 =59 −137 | 44.5% | −38 ± 16 | [folder](maurizio-platino/2026-09-11_coda-0.9.4) |
| 2026-09-14 | Caissa 1.26 BMI2 | 7.0, 2026-09-10 | 300 | +126 =65 −109 | 52.8% | +20 | [folder](maurizio-platino/2026-09-14_caissa-1.26) (result only) |
| 2026-09-22 | Caissa 2.0 BMI2 | 7.0, 2026-09-10 | 300 | +109 =59 −132 | 46.2% | −27 ± 15 | [folder](maurizio-platino/2026-09-22_caissa-2.0) |

**Conditions (all 7.0 matches)**

- Hardware: Intel Core i7-8700 @ 3.20 GHz
- GUI: Fritz 18
- 4 threads per engine, ponder on, 1024 MB hash per engine
- Time control: 1 min + 1 s per game, per engine
- Openings: `UHO_2024_8mvs_big_+110_+129.pgn` by Stefan Pohl (SPCC); 150 openings per match, each
  played twice with colours reversed

**How to read the numbers.** The Elo column and the W/D/L come from the game files and agree with
the GUI's crosstables (the `.png` in each folder). The ± is a 95% interval computed on the 150
opening pairs (pentanomial), which is the correct error for a book played with both colours. The
Caissa 1.26 match has only the crosstable, no games, so it has no interval. UHO openings give the
side with the advantage a large edge: the white side won about 80% of all games, and most pairs
end one win each. Only the pairs where one engine converts both sides, or holds the worse side,
move the score.

`7.0 dev, 2026-08-14` is a development build from about a month before the release; `7.0,
2026-09-10` carries the release date.

## Maurizio Platino — Triumviratus 8.0 (development) against Caissa 2.0

The same opponent as the last 7.0 match, with 8.0 development builds.

| Date | Triumviratus build | Threads · ponder | Games | +W =D −L | Score | Elo (Triumviratus) | Files |
|---|---|---|---:|---|---:|---:|---|
| 2026-09-30 | 8.0 dev, 2026-09-30 | 4 · on | 300 | +108 =61 −131 | 46.2% | −27 ± 15 | [folder](maurizio-platino/2026-09-30_caissa-2.0) |
| 2026-10-01 | 8.0 dev, 2026-10-01 | 4 · on | 300 | +113 =62 −125 | 48.0% | −14 ± 15 | [folder](maurizio-platino/2026-10-01_caissa-2.0) |
| 2026-10-03 | 8.0 dev, 2026-10-01 | 1 · off | 300 | +125 =59 −116 | 51.5% | +10 ± 14 | [folder](maurizio-platino/2026-10-03_caissa-2.0_1-thread) |

Opponent Caissa 2.0 BMI2. Same hardware, GUI, hash, time control and openings as above; only the
threads and ponder change, as listed. The game files only, without the crosstable images.

## Layout

```
maurizio-platino/<date>_<opponent>/
    triumviratus-<build>_vs_<opponent>.pgn   all games, as exported by Fritz (evals, times, depths in comments)
    triumviratus-<build>_vs_<opponent>.png   the GUI's final crosstable
```
