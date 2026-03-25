# QA Test Report Stack Cube

## 1. Overview

**Stack Cube** is a hyper-casual game where the player stacks moving blocks to build a tower.

The objective is to align each cube as accurately as possible. Misalignment reduces the size of the next cube, and failing to overlap results in game over.

The gameplay focuses on timing, alignment accuracy, size reduction mechanics, and stacking progression.

Testing focuses on alignment logic, size calculation, perfect placement detection, falling piece behavior, and game over conditions.

---

## 2. Test Cases

| ID | Test Case | Steps | Expected | Result |
| --- | --- | --- | --- | --- |
| SC01 | Cube movement | Observe moving cube | Cube moves smoothly along axis | OK |
| SC02 | Place cube normally | Click to place cube | Cube stacks on previous cube | OK |
| SC03 | Perfect placement | Align cube perfectly and click | Cube snaps exactly, no size loss | OK |
| SC04 | Partial overlap | Place cube slightly off center | Cube size reduces correctly | OK |
| SC05 | No overlap (miss) | Place cube completely off | Game over triggered | OK |
| SC06 | Alternating axis | Stack multiple cubes | Movement alternates between X and Z | OK |
| SC07 | Falling piece behavior | Create overhang while placing | Cut piece falls down correctly | OK |
| SC08 | Continuous stacking | Stack many cubes continuously | Tower builds upward consistently | OK |
| SC09 | Small cube limit | Continue stacking with small cubes | Cube remains controllable | FAIL – Precision issues at very small size |

---

## 3. Bug Reports

| Title | Steps | Expected | Actual | Severity |
| --- | --- | --- | --- | --- |
| Falling piece is Pink | 1. Create cut off parts by place the cube imperfectly | Falling piece drops off with grey color | falling pieces are in pink | Medium |
| Perfect detection inconsistency | 1. Attempt near-perfect placement | Perfect triggers consistently | Sometimes not detected | Medium |
| Prefab cubes sometimes stuck when patrolling | 1.Start the game and wait | Prefab cube moving back and forth perfectly | Sometimes the cubes stuck at the edge | High |
| Blurry Screen | 1.Start the game | perfectly clear screen | Blurry and low quality looking. | Medium |
| Delay sound effect | 1.Reach Game Over State | Perfectly matched Sound effect | Sound effect of the tower breaking delays by half a second | Low |
| UI deviation | 1.Manually reach idle state, playing state and game over state. | UI centered at middle of the screen | All UI on all states are deviated to the right | Medium |

---

## 4. Edge Cases

| Case | What happens | Result |
| --- | --- | --- |
| Very small cube stacking | Continue after many cuts | FAIL – Hard to control placement |
| Perfect spam attempts | Try repeated perfect placements | OK – System handles correctly |

---

##
