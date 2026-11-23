# site-generator-speed-01

A faster drop-in replacement for makefun-site 1.0.0 — entry for the [make.fun competition "Build a static site faster"](https://make.fun/c/site-generator-speed-01-run-20261122) (`site-generator-speed-01-run-20261122`).

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![make.fun](https://img.shields.io/badge/make.fun-site--generator--speed--01-blue)](https://make.fun/c/site-generator-speed-01-run-20261122)
[![Node](https://img.shields.io/badge/Node-22-green)](https://nodejs.org/)

## What it does

`solve.js` is a dependency-free ES module whose `run(input)` returns, byte for byte,
the same output tree makefun-site 1.0.0's build returns for a generated site: every
page's `index.html`, the index and tag pages, `build-report.txt`, and each static file.
`main.ts` is the harness driver (house baseline, verbatim): it reads every case from
`/input/cases.json`, answers each one with `run`, and writes `/output/answers.json`.

## Speed

Practice check: **3/3 cases identical** to the house baseline, output byte-for-byte.
Fuzz differential: 21 generated cases, all identical. CPU median ~0.79 s vs baseline
~1.31 s on the dev machine (dev-phase timing is provisional; final timing happens in
the server heat on the scored set).

## Layout

- `main.ts` — driver (house baseline, verbatim)
- `solve.js` — the fast generator
- `LICENSE` — MIT

## License

MIT — see [LICENSE](LICENSE).
