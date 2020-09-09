# Takuzu (Binairo) Puzzle Generation

This project investigates a popular Dutch puzzle by my girlfriend's request. I implemented a standard backtracking algorithm and a selection of human solving strategies with the goal of producing random, valid, deterministic and non-trivial puzzles. 

The generation process follows four steps:
1. An empty field is solved using random backtracking, producing a filled, unique and valid puzzle. 
2. Obvious redundancies are removed.
3. Additional tokens are iteratively removed at random, while ensuring the result is still solvable by the human algorithm. The still solvable puzzle received after removing the maximum number of tokens is the *puzzle candidate*.
4. If the *candidate* has too little empty slots (too easy), the algorithm goes back to step 1.

This process reliably creates puzzles with up to 70% empty slots, commonly classified as Medium difficulty.

## Open Issues
- Code additional human strategies
- How do we measure puzzle difficulty? Percentage of empty slots should not be the only metric.
- Formulating and solving the puzzle as a Constraint-Satisfaction-Problem may be faster than backtracking. However unclear whether this is the bottleneck.
