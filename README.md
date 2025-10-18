# Information-Theoretic Wordle Solver

This project treats **Wordle as a sequential inference problem** rather than a guessing game. Each guess provides structured feedback from which we can **shrink the hypothesis space**. We apply **Shannon’s greedy decision tree strategy** to minimize expected uncertainty at every step using **partition-based information gain**.

This repository contains a **strict-mode Wordle solver** that:
- Plays interactively with the user
- Suggests **optimal next guesses**
- Uses **no heuristics** and **no frequency hacks**
- Relies purely on **information theory and search**
- Guarantees **correct logical inference** consistent with feedback

---

## 🔧 Approach

At round \( t \), we maintain a candidate set \( \mathcal{S}_t \subseteq \mathcal{S} \), updated by posterior filtering:

\[
\mathcal{S}_{t+1} = \{\, w \in \mathcal{S}_t \mid F(g_t, w) = y_t \,\}.
\]

Each guess induces a **partition** of the current search space into feedback buckets:

\[
C_y(g) = \{\, w \in \mathcal{S}_t \mid F(g, w) = y \,\}.
\]

To choose the optimal next guess, we minimize the **expected remaining search space**:

\[
J(g) = \sum_y |C_y(g)|^2.
\]

This implements a **greedy information gain strategy** equivalent to Shannon-optimal decision trees.

---

## ✅ Features

- Strict Wordle rules (valid dictionary guesses only)
- Feedback-aware hypothesis elimination
- Information-theoretic next move suggestion
- Worst-case-aware tie-breaking
- Always logical, never random
- Extendable framework (probe mode, larger alphabets, adversarial inference)

---

## 🚀 Usage

```bash
git clone https://github.com/yourname/wordle-inference-engine.git
cd wordle-inference-engine
python solver.py
