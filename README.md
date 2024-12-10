# Bash Script Bug: Incorrect File Processing

This repository demonstrates a common error in shell scripting involving the incorrect use of `while` loops to process files.  The script attempts to process files in a directory, but due to the nested while loop, it processes each file line by line instead of treating each file as a single unit. This leads to unexpected behavior and incorrect file handling.  The `bugSolution.sh` file provides the corrected version.

## Bug Description
The bug lies in how the script iterates through files. Using a nested `while IFS= read -r line` loop within the loop that iterates through files using `find` means that each line of each file is treated as a separate unit, rather than the file as a whole. This makes the script unsuitable for processing the content of a file as a unit, which is a common requirement in many shell scripts.

## Solution
The solution involves removing the inner `while` loop and directly using the file content within the outer loop.