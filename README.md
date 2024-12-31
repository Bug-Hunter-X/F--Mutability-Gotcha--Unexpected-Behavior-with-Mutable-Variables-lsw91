# F# Mutability Gotcha: Unexpected Behavior with Mutable Variables

This example demonstrates a potential pitfall when working with mutable variables in F#.  The `add` function uses the values of `x` and `y` at the time it's called, and subsequent changes to `x` and `y` don't affect the result of `add`.

## Files

* **bug.fs**: Demonstrates the unexpected behavior.
* **bugSolution.fs**: Shows how to modify the code for the expected behavior, making it clear how mutability works.

## How to Reproduce

1. Compile and run `bug.fs`. You will observe that the output is not what one might initially expect given the later assignments to `x` and `y`.
2. Compile and run `bugSolution.fs` to see the corrected behavior.

## Problem and Solution

The problem arises from the fact that F# passes values to functions by value (unless using references explicitly).  The solution either involves passing references or recalculating the sum after modifying the variables.