---
layout: page
title: Haskell Expression Calculator
description: Command-line arithmetic calculator in Haskell using prefix (Polish) notation, with recursive algebraic data types and the Maybe monad.
img: assets/img/project_img/8.png
importance: 8
category: work
github: https://github.com/SujitBhatta21/ExpressionCalculator
tech:
  - haskell/haskell-plain
---

A Haskell REPL that evaluates arithmetic expressions written in prefix (Polish) notation - built as a personal exercise in functional programming after completing coursework.

```
INPUT: + * 2 3 / 8 4
Result: 8        -- (2 * 3) + (8 / 4)
```

---

## Features

- Supports `+`, `-`, `*`, `/` with arbitrary nesting
- Recursive parser using algebraic data types (`Expr`)
- Safe parsing via the `Maybe` monad - invalid input returns an error, no crashes
- Readline support via `haskeline` (arrow keys, backspace in REPL)

---

## Tech Stack

<p>
  <img src="https://img.shields.io/badge/Haskell-GHC-5D4F85?style=flat-square&logo=haskell&logoColor=white" alt="Haskell"/>
  <img src="https://img.shields.io/badge/Haskeline-REPL-5D4F85?style=flat-square" alt="Haskeline"/>
</p>