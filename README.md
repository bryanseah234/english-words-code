# English Words Code

A Python script that generates all possible letter combinations from 1 to 26 characters long.

## Description

This project generates every possible combination of lowercase English letters for words of varying lengths (1-26 characters). It systematically creates all permutations using nested loops and outputs them to a text file. This can be useful for understanding combinatorics, brute-force wordlist generation, or educational purposes in learning Python.

## Features

- Generates all single-letter combinations (a-z)
- Generates all multi-letter combinations up to 26 characters
- Outputs all combinations to a `words.txt` file
- Prints each combination to the console for real-time progress

## Technologies Used

- Python 3

## Installation

```bash
# Clone the repository
git clone https://github.com/bryanseah234/english-words-code.git

# Navigate to project directory
cd english-words-code
```

## Usage

```bash
# Run the script
python englishwords.py
```

**Note:** This script generates an extremely large number of combinations (26^n for each word length n). Running the full script will likely result in memory errors and may take an impractical amount of time to complete. For practical use, consider modifying the script to generate only shorter word lengths.

## Disclaimer

1. FOR EDUCATIONAL PURPOSES ONLY
2. USE AT YOUR OWN DISCRETION
3. Running the full script will likely cause memory errors due to the exponential growth of combinations

## License

MIT License

---

**Author:** <a href="https://github.com/bryanseah234">bryanseah234</a>
