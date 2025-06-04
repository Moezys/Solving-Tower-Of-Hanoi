Tower of Hanoi Recursive Solver
This Python script implements the classic Tower of Hanoi puzzle using a recursive algorithm. Given a specified number of disks stacked in decreasing size on rod A, it moves the entire stack to rod C following the game’s rules:

Only one disk can be moved at a time.

A disk can only be placed on top of a larger disk (never on a smaller one).

There are three rods: a source (A), an auxiliary (B), and a target (C).

Overview
When you run this script, it will:

Initialize three rods, A, B, and C, where:

A begins with all disks, numbered from largest (bottom) to smallest (top).

B and C start empty.

Recursively move the entire stack of disks from A to C, using B as an auxiliary rod.

Print the state of rods A, B, and C after each individual disk move, so you can observe the step-by-step solution.

By default, NUMBER_OF_DISKS = 5, but you can change this constant to solve for more or fewer disks.

How It Works
Initialization

NUMBER_OF_DISKS = 5
A = list(range(NUMBER_OF_DISKS, 0, -1))  # [5, 4, 3, 2, 1]
B = []
C = []
A is constructed with disks 5, 4, 3, 2, 1 (5 at bottom, 1 at top).

Rods B and C are empty lists.

Recursive Function Definition: move(n, source, auxiliary, target)

def move(n, source, auxiliary, target):
    if n <= 0:
        return

    # 1. Move n−1 disks from source → auxiliary (to free up the largest disk).
    move(n - 1, source, target, auxiliary)

    # 2. Move the nth (largest remaining) disk from source → target.
    target.append(source.pop())
    print(A, B, C, '\n')

    # 3. Move the n−1 disks from auxiliary → target (stack on top of the largest disk).
    move(n - 1, auxiliary, source, target)
Base Case: When n <= 0, do nothing (no disks to move).

Recursive Step:

Move the top n−1 disks off of source and onto auxiliary (using target as an intermediate).

Pop the last disk from source (the nth disk) and append it onto target.

Print the three rods to show current state.

Move the n−1 disks from auxiliary onto target, using source as intermediate.

Starting the Algorithm

move(NUMBER_OF_DISKS, A, B, C)
This call solves the entire puzzle by moving all disks (1 through 5) from A to C.

Requirements
Python 3.6+ (any modern Python 3 version will work).

No external libraries—this is a pure-Python recursive solution.

License
This code is released under the MIT License. Feel free to use, modify, and redistribute as you wish, as long as you include this license notice.

Enjoy exploring the Tower of Hanoi and studying how recursion elegantly solves this puzzle!
