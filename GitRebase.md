# Real-Time Git Rebase Example

## Situation

Tum ek e-commerce company mein kaam kar rahe ho.

---

## Main Branch

Production code:

```text
main

A = Project setup
B = Product page
C = Cart page
```

```text
A --- B --- C
```

---

## Tumhari Feature Branch

Tumhe Coupon Feature banana hai.

```bash
git switch -c feature-coupon
```

Tumne 2 commits kiye:

```text
D = Add coupon UI
E = Add coupon validation
```

History:

```text
A --- B --- C
            \
             D --- E
```

---

## Meanwhile...

Tum 3 din se coupon feature par kaam kar rahe ho.

Dusre developers ne `main` mein commits kar diye:

```text
F = Payment bug fix
G = Tax calculation fix
```

Ab:

```text
A --- B --- C --- F --- G   (main)
            \
             D --- E        (feature-coupon)
```

---

## Problem

Ab tumhara feature purane code (`C`) par based hai.

Agar abhi PR bhejoge:

* Conflicts aa sakte hain
* Payment changes test nahi hue
* Latest production code feature mein nahi hai

---

## Solution: Rebase

Feature branch par jao:

```bash
git switch feature-coupon
```

Rebase:

```bash
git rebase main
```

Git internally:

```text
1. D ko hatao
2. E ko hatao

A-B-C-F-G

3. D dubara lagao
4. E dubara lagao
```

Result:

```text
A --- B --- C --- F --- G --- D' --- E'
```

---

## Ab Kya Fayda Hua?

Tumhare feature branch mein:

✅ Payment bug fix aa gaya

✅ Tax calculation fix aa gaya

✅ Latest main ke saath testing ho gayi

✅ History clean hai

---

## Rebase Na Karte To?

Agar merge karte:

```bash
git merge main
```

History:

```text
A --- B --- C --- F --- G
            \           \
             D --- E ---- M
```

`M` = Merge Commit

Project mein 100 developers hon to aise hundreds merge commits ban jate hain.

---

## Real Daily Workflow

Senior developers aksar:

```bash
git fetch origin

git switch feature-coupon

git rebase origin/main
```

Phir:

```bash
git push --force-with-lease
```

Aur PR create kar dete hain.

---

## Interview Answer Version

Agar interviewer puche:

**"Why do we use git rebase?"**

Answer:

> "Suppose I'm working on a feature branch and meanwhile new commits are added to main. I use git rebase main to replay my feature commits on top of the latest main branch so that my feature contains the newest changes and the commit history remains clean and linear."

Ye answer industry mein bilkul sahi maana jata hai.
