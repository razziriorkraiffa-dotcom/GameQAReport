# QA Test Report Hole.IO

## 1. Overview

**Hole.io Clone** is a hyper-casual game where the player controls a hole that consumes objects to grow in size.

The objective is to absorb smaller objects to increase size and eventually consume larger objects as the game progresses.

The gameplay focuses on smooth movement, accurate collision detection, object interaction, and scaling mechanics.

Testing focuses on consumption logic, size progression, collision accuracy, object interaction, and performance under increasing object counts.

---

## 2. Test Cases

| ID | Test Case | Steps | Expected | Result |
| --- | --- | --- | --- | --- |
| HO01 | Player movement | Move hole using input | Hole moves smoothly | OK |
| HO02 | Consume small object | Move over small object | Object disappears, size increases | OK |
| HO03 | Cannot consume large object | Move over large object (early game) | Object remains, no consumption | OK |
| HO04 | Size progression | Consume multiple objects | Hole size increases gradually | OK |
| HO05 | Consume larger objects after growth | Grow hole → revisit object | Object now consumable | OK |
| HO06 | Multiple object consumption | Move over cluster of objects | Objects consumed smoothly | OK |
| HO07 | Object overlap handling | Objects close together | Correct consumption order | FAIL – Some objects not consumed |
| HO08 | Boundary collision | Move to map edge | Player stays within bounds | OK |

---

## 3. Bug Reports

| Title | Steps | Expected | Actual | Severity |
| --- | --- | --- | --- | --- |
| Object not consumed | 1. Move over small object cluster | All objects consumed | Some objects remain | Medium |
| Object visually bugged when consumed on grass platform | 1. Consume object in grass platform | Objects fall through the hole and get consumed | Objects fall off the ground instead of falling into the hole | High |
| Collision inconsistency | 1. Move across object edge | Object consumed correctly | Missed or delayed consumption | Medium |
| Big object falls off the ground | 1. Move to an object that is bigger than the hole<br>2. Move the hole away immediately | Object stays still, no interaction | Object bumps up briefly then falls off the ground | High |

---

## 4. Edge Cases

| Case | What happens | Result |
| --- | --- | --- |
| Rapid movement over objects | Move very fast across map | FAIL – Missed collisions |
| Consume objects at boundary size | Size just enough to consume | FAIL – Inconsistent detection |
| Overlapping objects | Objects stacked together | FAIL – Some objects ignored |

---

##
