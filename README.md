Our boss wants to be able to access astronaut names from individual files now. We told him that this was not going to help get us to space, but he insists that he needs the stars to align in our favor. Typical Scorpio. Anyway, listen, you don't need to worry about creating those files or anything for right now. He already has them, but he wants to be able to open them using your software. Opening files will come in handy later.

Please write a program that asks the user to enter the name of a file, and then asks the user to enter a letter. The program should count and display the number of times that letter appears in the file (just like last time).

Five files are already provided in this project for you to test with: `astronaut1.txt`, `astronaut2.txt`, `astronaut3.txt`, `astronaut4.txt`, and `astronaut5.txt`. Each one contains a single line with one astronaut's name. When the user is asked for a file name, they should type one of these names exactly, including the `.txt` extension (for example, `astronaut1.txt`).

You can recycle a lot of code from the last assignment. This type of change to add functionality to an old piece of software is referred to as "iterative design," and it is how most engineering, including software and aerospace, works. Everyone is iterating everything all the time. Don't feel bad if your code is basic at first. Windows was written one line at a time.

## What you're building

A program that:

1. Asks the user for a file name and reads that file from disk.
2. Asks the user for a letter to search for.
3. Counts how many times that letter appears anywhere in the file, **regardless of whether the letter in the file or the letter typed by the user is uppercase or lowercase**.
4. Displays the count.

If the letter does not appear in the file at all, the program should still display a result, reporting a count of `0`.

## Concepts you'll need

- `Scanner` to read the file name and letter from the keyboard.
- File reading (we suggest `FileReader` and `BufferedReader`, like the comments in the starter code do).
- A loop to read every line of the file.
- A nested loop (or equivalent) to check every character in each line.
- Converting text to uppercase so that matching works no matter what case the user or the file uses.

## Required prompts and output

Your program must display these prompts, in this order:

- `Please enter the name of the file.`
- `Enter a letter that you want counted.`

After counting, display the result in this exact format, using the uppercase version of the letter the user entered:

```
The letter N appears 2 times in that file.
```

For example, if the user enters `astronaut1.txt` and then `n`, your program should report that the letter `N` appears `2` times, since `astronaut1.txt` contains the name "Neil Armstrong."
