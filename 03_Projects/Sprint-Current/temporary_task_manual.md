
##  User Story

As an iPID user, I want symbols to maintain proper spacing after grid alignment, so that the DEXPI output remains readable and does not require manual repositioning.

---

## Issue Summary

After grid alignment, certain detected symbols overlap in the DEXPI output.

This issue is primarily observed in the file **"EPL-1000-P-FP 2501.pdf"**, particularly affecting:

- Valves
    
- Reducers
    
The overlapping behavior may be related to the current grid resolution settings.

---

## Root Cause

The `align_graph_to_grid()` function in `grid.py` appears to snap symbols to grid points without enforcing minimum spacing constraints between neighboring symbols.

As a result, symbols that were originally positioned close to one another may be shifted onto the same or adjacent grid coordinates, leading to visual overlap in the exported DEXPI output.
