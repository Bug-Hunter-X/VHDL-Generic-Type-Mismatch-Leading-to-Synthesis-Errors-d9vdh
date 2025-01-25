# VHDL Generic Type Mismatch Bug Report

This repository demonstrates a common, yet subtle, error in VHDL code involving the incorrect use of generics.  Specifically, this example highlights the issue of using an integer type generic where a natural type is required. 

The `bug.vhdl` file contains the erroneous code, while `bugSolution.vhdl` shows the corrected version. The problem stems from the difference between the ranges of `integer` (which includes negative values) and `natural` (non-negative values).  This mismatch can lead to synthesis failures or unexpected results during simulation.

## How to Reproduce

1.  Synthesize `bug.vhdl` using your preferred VHDL synthesis tool.
2.  Observe the synthesis errors or unexpected behavior.
3.  Synthesize `bugSolution.vhdl` for comparison.

## Solution

The solution involves simply changing the generic's type from `integer` to `natural`. This ensures that only non-negative values are accepted, eliminating the potential for synthesis issues or runtime problems.