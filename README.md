# ExpNo 8: Solve Cryptarithmetic Problem, a CSP (Constraint Satisfaction Problem) Using Python

### Name:
DHANALAKSHMI C

### Register Number/Staff ID:
212225230050

## AIM

To solve a Cryptarithmetic Problem, a Constraint Satisfaction Problem (CSP), using Python.

## THEORY

A cryptarithmetic problem is a mathematical puzzle in which each letter represents a unique digit from 0 to 9. The objective is to assign digits to letters so that the given arithmetic equation is correct.

In this experiment, the problem **SEND + MORE = MONEY** is solved using Python. The program checks possible digit assignments and finds a valid solution.

## PROCEDURE

1. Start the program.
2. Import the `permutations` function from the `itertools` module.
3. Define the words SEND, MORE, and MONEY.
4. Identify all unique letters in the words.
5. Generate possible digit assignments from 0 to 9.
6. Ensure that the first letters of the words are not assigned zero.
7. Check whether the numerical values satisfy SEND + MORE = MONEY.
8. Display the valid digit assignments.
9. Stop the program.

## PROGRAM

```python
from itertools import permutations

letters = 'SENDMOREY'

for digits in permutations(range(10), len(letters)):
    d = dict(zip(letters, digits))

    if d['S'] == 0 or d['M'] == 0:
        continue

    SEND = (d['S'] * 1000 + d['E'] * 100 +
            d['N'] * 10 + d['D'])

    MORE = (d['M'] * 1000 + d['O'] * 100 +
            d['R'] * 10 + d['E'])

    MONEY = (d['M'] * 10000 + d['O'] * 1000 +
             d['N'] * 100 + d['E'] * 10 + d['Y'])

    if SEND + MORE == MONEY:
        print("Solution Found:")
        print("SEND =", SEND)
        print("MORE =", MORE)
        print("MONEY =", MONEY)
        print("\nLetter to Digit Mapping:")

        for letter in letters:
            print(letter, "=", d[letter])

        break
```
## Programe

```
from itertools import permutations

def solve_cryptarithmetic():
    for perm in permutations(range(10), 8):
        S, E, N, D, M, O, R, Y = perm

        # Check for leading zeros
        if S == 0 or M == 0:
            continue

        # Calculate the numbers
        SEND = 1000 * S + 100 * E + 10 * N + D
        MORE = 1000 * M + 100 * O + 10 * R + E
        MONEY = 10000 * M + 1000 * O + 100 * N + 10 * E + Y

        # Check the equation
        if SEND + MORE == MONEY:
            return SEND, MORE, MONEY

    return None

# Call the function
solution = solve_cryptarithmetic()

if solution:
    SEND, MORE, MONEY = solution
    print(f"SEND = {SEND}")
    print(f"MORE = {MORE}")
    print(f"MONEY = {MONEY}")
else:
    print("No solution found.")
```
## SAMPLE OUTPUT

```text
Solution Found:
SEND = 9567
MORE = 1085
MONEY = 10652

Letter to Digit Mapping:
S = 9
E = 5
N = 6
D = 7
M = 1
O = 0
R = 8
Y = 2
```
## Output
<img width="332" height="85" alt="Screenshot 2026-10-28 083400" src="https://github.com/user-attachments/assets/f68bd31a-d2e1-4b2a-ae3d-aea130a48e9d" />

## RESULT

Thus, the Cryptarithmetic Problem, a Constraint Satisfaction Problem (CSP), was solved successfully using Python.
