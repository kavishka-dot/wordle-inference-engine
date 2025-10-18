# Information-Theoretic Wordle Solver

wordlegame.drawio.png


This project treats **Wordle as a sequential inference problem** rather than a guessing game. Each guess provides structured feedback from which we can **shrink the hypothesis space**. We apply **Shannon’s greedy decision tree strategy** to minimize expected uncertainty at every step using **partition-based information gain**.

This repository contains a **strict-mode Wordle solver** that:
- Plays interactively with the user
- Suggests **optimal next guesses**
- Uses **no heuristics** and **no frequency hacks**
- Relies purely on **information theory and search**
- Guarantees **correct logical inference** consistent with feedback

---

## ✅ Features

- Strict Wordle rules (valid dictionary guesses only)
- Feedback-aware hypothesis elimination
- Information-theoretic next move suggestion
- Worst-case-aware tie-breaking
- Always logical, never random
- Extendable framework (probe mode, larger alphabets, adversarial inference)


