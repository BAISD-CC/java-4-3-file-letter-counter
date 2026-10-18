# Ch. 4 Challenge 3: File Letter Counter

## Mission Briefing

Mission Control now keeps each astronaut's name in its own text file, and the boss wants to open those files with your software. Your program asks which file to open and which letter to count, then reports how many times that letter appears in the file. The counting works just like Challenge 4-2; the name now comes from a file instead of the keyboard. Adding a feature to working code like this is called iterative design, and it is how most software and aerospace engineering gets done.

## What You'll Practice

- Reading a file with `File` and `Scanner`, looping with `hasNext()` (Day 3 notes, FR2 and FR3)
- A `for` loop through every character of a String with `charAt()` (Day 2 notes, F3)
- A counter that adds 1 each time something matches (Day 2 notes, R2)
- `toUpperCase()` (Chapter 2) and `throws IOException` (Day 3 notes, Writing Files)

## Starter Code

Edit `src/FileLetterCounter.java`. The class is `FileLetterCounter`. Do not rename the file or the class.

The comments list the steps in order. The starter already imports `java.io.*` and declares the exceptions on `main`; add `import java.util.Scanner;` yourself. The comments suggest `FileReader` and `BufferedReader`, but the `File` and `Scanner` approach from class works just as well and earns full credit. Close the keyboard `Scanner` and the file when you are done with them.

Five test files sit in the project folder (not in `src`): `astronaut1.txt` through `astronaut5.txt`. Each holds one astronaut's name on one line. When the program asks for a file name, type it exactly, including `.txt`.

## Inputs

| Order | What it is | Java type |
|---|---|---|
| 1 | The file name, for example `astronaut1.txt` | `String` |
| 2 | The letter to count (one character) | `String`, then its first character as a `char` |

## Rules

### 1. Count the whole file

Count the letter on every line of the file, not just the first. The test files have one line each, but your loop should keep reading until `hasNext()` is false.

### 2. The count ignores case

Upper case and lower case count as the same letter. Typing `n` counts every `N` and every `n`.

| File | Name inside | Letter typed | Count |
|---|---|---|---|
| `astronaut1.txt` | Neil Armstrong | `n` or `N` | 2 |
| `astronaut2.txt` | John Glenn | `n` | 3 |
| `astronaut3.txt` | Buzz Aldrin | `z` | 2 |

### 3. The result line

The result shows the letter in upper case, whatever case was typed. It always says `times`, even for a count of 1. If the letter never appears, the result still prints, with a count of `0`.

## What to Use

These are suggestions. Any approach that produces the correct output earns full credit, as long as it uses a `Scanner`, reads the file (`File`, `FileReader`, or `BufferedReader`), and uses a loop (see How It's Checked).

- `File file = new File(fileName);` and `Scanner inputFile = new Scanner(file);` to open the file the user named (FR2 pattern).
- A `while (inputFile.hasNext())` loop that reads one line at a time with `nextLine()`.
- Inside it, a `for` loop over the line's characters with `charAt()` (F3 pattern): a loop inside a loop.
- A counter that starts at 0 **before** the file loop, so it keeps counting across every line.
- `toUpperCase()` on each line and on the letter before comparing.

## Exact Output

Spelling, capitalization, and punctuation must match. Each prompt is printed on its own line; the user types on the next line.

First prompt:

```
Please enter the name of the file.
```

Second prompt:

```
Enter a letter that you want counted.
```

Result, after the file has been read:

```
The letter [LETTER] appears [count] times in that file.
```

`[LETTER]` is the letter the user typed, in upper case. `[count]` is a whole number. The line ends with a period.

## Sample Runs

```text
Please enter the name of the file.
astronaut1.txt
Enter a letter that you want counted.
n
The letter N appears 2 times in that file.
```

```text
Please enter the name of the file.
astronaut2.txt
Enter a letter that you want counted.
n
The letter N appears 3 times in that file.
```

The letter does not appear:

```text
Please enter the name of the file.
astronaut1.txt
Enter a letter that you want counted.
Z
The letter Z appears 0 times in that file.
```

## Test Your Program

Run each test before you submit. The autograder uses these and other values.

| File | Letter | Result line |
|---|---|---|
| `astronaut1.txt` | `Z` | `The letter Z appears 0 times in that file.` |
| `astronaut1.txt` | `N` | `The letter N appears 2 times in that file.` |
| `astronaut2.txt` | `n` | `The letter N appears 3 times in that file.` |
| `astronaut3.txt` | `z` | `The letter Z appears 2 times in that file.` |
| `astronaut4.txt` | `A` | `The letter A appears 3 times in that file.` |
| `astronaut5.txt` | `D` | `The letter D appears 2 times in that file.` |

## How It's Checked

| Check | What it looks for | Points |
|---|---|---|
| Prompts | Both prompts appear (1 point each) | 2 |
| Counting | The result line for astronaut1.txt with `N`, astronaut2.txt with `n`, and astronaut4.txt with `A` (4 points each), and astronaut5.txt with `D` (2 points) | 14 |
| No match | The result line with a count of 0 (astronaut1.txt, `Z`) | 3 |
| Uses a `Scanner` | The source code uses `Scanner` | 2 |
| Reads a file | The source code uses `File`, `FileReader`, `BufferedReader`, or `Files` | 2 |
| Uses a loop | The source code has a `while` or `for` loop | 2 |
| **Total** | | **25** |

Any approach that produces the correct output earns full credit, as long as it passes the three source checks. Results must come from the file the user names; the tests use several different files and letters.

## Where to Look

- Day 3 notes, FR2 (reading every line) and FR3 (`exists()` and a `hasNext()` loop).
- Day 2 notes, F3 (walking through a String) and R2 (a counter).
- Your own Challenge 4-2 code: the counting loop is the same idea.
- Rule 2 above: which letters count as a match.
