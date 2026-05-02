# PRD: englishwords

## Overview
A Python script that generates every possible lowercase alphabetic string from length 1 to N (demonstrated up to 26) and writes them all to `words.txt`. Built as a combinatorics demonstration — essentially a brute-force word list generator using pure nested loops instead of `itertools`. Primarily an educational exercise in loop nesting and exponential growth.

## Goals
- Generate all lowercase alphabetic strings from length 1 to target length
- Write each generated string to `words.txt` with one string per line
- Demonstrate nested-loop approach to combinatorial generation

## Non-Goals
- Filtering by actual English words (no dictionary check)
- Memory-efficient streaming (loads all in RAM)
- Performance optimization (no itertools, no generators)
- Command-line arguments for length or alphabet

## User Stories
- As a security researcher, I want a complete wordlist of all possible lowercase combinations up to length N for brute-force testing.
- As a student, I want to understand how nested loops generate all string permutations.

## Tech Stack
- **Language**: Python 3.x
- **Libraries**: stdlib only (`open`, string operations)

## Architecture
```
englishwords/
├── englishwords.py   # One function per length (one() through twentysix())
└── words.txt         # Output (generated)
```

**Structure:**
- 26 functions `one()` through `twentysix()`, each with N nested `for` loops over `'abcdefghijklmnopqrstuvwxyz'`
- `one()` → 26 strings, `two()` → 676, `three()` → 17,576, up to 26^N
- Main block opens `words.txt` in write mode, calls each function in sequence

## Features

### Word Generation
- Character set: `a-z` (26 lowercase letters only)
- Length range: 1 to N (26 functions defined; calling all would require astronomical storage)
- Each function builds and returns a list — **entire list held in RAM** before writing
- Practically usable up to length ~5-6; beyond that: memory/time become prohibitive

### Output
- Plain text file, one word per line
- Overwrites `words.txt` on each run

## Deployment / Run
```bash
python englishwords.py
```
**Warning:** calling all 26 functions is computationally infeasible. Edit `englishwords.py` to call only `one()` through `four()` for practical use.

## Constraints & Notes
- **Exponential growth**: 26^6 = 308 million strings ≈ 2+ GB of text — running `six()` and beyond requires significant storage and RAM
- **No itertools**: intentionally uses nested loops for educational demonstration
- **Memory**: each function returns a full list before writing — not memory-streamed
- **Performance**: `seven()` through `twentysix()` are defined but impractical to run in any reasonable time
- **Better alternative**: `itertools.product(string.ascii_lowercase, repeat=N)` with streaming write achieves the same result with O(1) memory
