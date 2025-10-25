# Hooks 11 - Complete Solution (from first principles)

**Deliverable:** [`Hooks11_Solution.pdf`](./Hooks11_Solution.pdf)

This repository contains a rigorous, self-contained write-up solving the Jane Street puzzle **“Hooks 11.”** The PDF formalises all rules, gives a precise constraint model, presents the human deductions that force the unique layout, and computes the required submission value.

---

## What’s inside the PDF

- **Problem formalisation**  
  Clear statement of all constraints: digit multiset, connectivity, no 2×2, nine *distinct* pentominoes, per-pentomino sums ≡ 0 (mod 5), hook membership, and the “first-seen” border clues.

- **Constraint model (certificate of correctness)**  
  A solver-agnostic model (suitable for CP-SAT / MILP) that uniquely identifies the final grid under the printed hooks and border sightlines.

- **Human deductions (search-free)**  
  Forced placements of the nine pentominoes (I, U, L, F, X, T, N, Z, V) with coordinates that preserve connectivity and avoid any 2×2 fill.

- **Digit assignment**  
  Consistent with the multiset (exactly `d` copies of digit `d`, for `d=1..9`) and per-pentomino mod-5 sums.

- **Result**  
  The empty cells split into nine connected regions with sizes  
  `(1, 1, 1, 1, 1, 3, 4, 9, 15)` → product **`1620`**.

---

## Quick facts

- **Grid:** 9×9 with nine nested L-shaped hooks (sizes 17, 15, 13, 11, 9, 7, 5, 3, 1).  
- **Digits:** exactly `d` copies of digit `d` for `d=1..9` (45 filled cells total).  
- **Tiling:** nine **distinct** pentominoes (no repeats under rotation/reflection).  
- **No 2×2:** no fully filled 2×2 block anywhere.  
- **Per-pentomino sums:** multiples of 5.  
- **Border “first-seen”:**  
  - Top: **column 7 → digit 7**  
  - Bottom: **column 3 → digit 3**  
  - Left (rows 1,4,5,9): **I, 6, N, Z**  
  - Right (rows 1,4,6,9): **U, X, 2, V**

These conditions force a **unique** arrangement, shown and proved in the PDF.

---

## How to use this repo

- Open the PDF: [`Hooks11_Solution.pdf`](./Hooks11_Solution.pdf)  
- If you want to implement a checker later, the PDF includes a solver-agnostic constraint specification you can translate into CP-SAT / MILP. (This repository does **not** include code.)

---

## Verification summary (as proved in the PDF)

- Digit counts: `{1:1, 2:2, …, 9:9}`  
- 45 filled cells, **single connected component** (4-neighbour)  
- **No** 2×2 fully filled block  
- Exactly **nine** pentomino labels, each **size 5**, all **distinct** shapes  
- Each pentomino’s digit sum ≡ 0 (mod 5)  
- All “first-seen” border clues satisfied  
- Empty regions: sizes `(1, 1, 1, 1, 1, 3, 4, 9, 15)` → product **`1620`**

---

## Credits

- Original puzzle: Jane Street's “Hooks 11”  
  https://www.janestreet.com/puzzles/hooks-11-index/

This repository provides an independent formal solution write-up only.


