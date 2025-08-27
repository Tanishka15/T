# Trading OA Probability & Combinatorics — One‑Pager

## Core Rules (remember these fast!)
- **Sample space size**: Count equally likely outcomes.
- **Complement**: P(Aᶜ) = 1 − P(A).
- **Addition rule**: P(A ∪ B) = P(A) + P(B) − P(A ∩ B).
- **Multiplication rule (independence)**: If A, B independent ⇒ P(A ∩ B) = P(A)P(B).
- **Conditional probability**: P(A|B) = P(A ∩ B) / P(B).
- **Bayes' rule**: P(A|B) = P(B|A)P(A) / P(B).

## Counting
- **Permutations**: _nP r_ = n! / (n−r)!  
- **Combinations**: _nC r_ = n! / (r!(n−r)!)
- **With replacement**: independent trials, multiply probabilities.
- **Without replacement**: adjust numerators/denominators step by step (Hypergeometric).

## Distributions you actually use
- **Binomial** (n trials, success prob p): P(K=k) = C(n,k) p^k (1−p)^{n−k};  E[K]=np.
- **Geometric** (trials until 1st success, prob p): P(K=k)= (1−p)^{k−1} p;  E[K]=1/p.
- **Hypergeometric** (no replacement): P(k successes) = C(K,k) C(N−K, n−k) / C(N, n).

---

## Worked micro‑examples (typical trading OA)

### 1) Two dice — sum > 9
All outcomes = 36. Favorable sums: **10, 11, 12**.  
- 10 → (4,6), (5,5), (6,4) = **3 ways**  
- 11 → (5,6), (6,5) = **2 ways**  
- 12 → (6,6) = **1 way**  
Total favorable = 3+2+1 = **6** ⇒ **P = 6/36 = 1/6 ≈ 16.67%**.

> Quick check: average sum is 7; tails are thinner; >9 should be modest (~1/6) — sanity‑check your count.

### 2) Balls without replacement
Urn: 5 red, 7 blue. Draw 2, no replacement.  
P(both red) = (5/12) × (4/11) = **20/132 = 5/33 ≈ 15.15%**.

> Pattern: multiply descending counts on top, descending totals on bottom.

### 3) Coin flips until first head
p(head) = 0.5. Expected flips **E = 1/p = 2**.  
General: if p ≠ 0.5, E = 1/p.

### 4) “Doesn’t happen 3 times”
If event happens with p=0.8 per trial, “doesn’t happen” per trial = 0.2.  
3 independent trials ⇒ **(0.2)^3 = 0.008 = 0.8%**.

### 5) Binomial quickies
- “Exactly k successes”: C(n,k) p^k (1−p)^{n−k}.  
- “At least one success”: 1 − (1−p)^n (use complement; it’s faster).

### 6) Market‑style estimation (Fermi)
Break problem into factors, use ranges, multiply:  
Daily rides ≈ Population × Users/day × Rides per user × Ticket.  
State assumptions, then refine.

---

## Dice grid (reference counts)
Sums and counts (ways):
2:1; 3:2; 4:3; 5:4; 6:5; 7:6; 8:5; 9:4; **10:3; 11:2; 12:1**.

> Symmetry tip: counts rise to 7 then mirror back down.

## Mental math nudges
- Use complements (≥1 success), round numbers, and symmetry.
- When stuck, **estimate**, then sanity‑check with bounds.
