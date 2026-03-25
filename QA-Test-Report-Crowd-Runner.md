# QA Test Report Crowd Runner

## 1. Overview

**Crowd Runner Clone** is a hyper-casual game where the player controls a group of units that grow or shrink based on interactions with gates, obstacles, and enemies.

The objective is to increase the crowd size, avoid losses, and reach the end while maintaining enough units to complete the level.

The gameplay focuses on crowd scaling, gate logic, collision handling, and performance with multiple units.

Testing focuses on unit behavior, gate calculations, collision outcomes, and system stability under large unit counts.

---

## 2. Test Cases

| ID | Test Case | Steps | Expected | Result |
| --- | --- | --- | --- | --- |
| CR01 | Player movement | Move crowd left/right | Crowd follows input smoothly | OK |
| CR02 | Gate addition (+) | Pass through + gate | Unit count increases correctly | OK |
| CR03 | Gate multiplication (x) | Pass through x gate | Unit count multiplies correctly | OK |
| CR04 | Obstacle collision | Hit obstacle | Units decrease accordingly | OK |
| CR05 | Enemy collision | Hit enemy group | Units decrease based on enemy size | OK |
| CR06 | Large crowd behavior | Grow crowd large | Units move together without breaking formation | OK |
| CR07 | Unit spacing | Observe crowd movement | Units maintain proper spacing | FAIL – Units overlap at high count |
| CR08 | Finish line | Reach end with units | Level completes correctly | OK |

---

## 3. Bug Reports

| Title | Steps | Expected | Actual | Severity |
| --- | --- | --- | --- | --- |
| Unit overlap at high count | 1. Grow large crowd | Units maintain spacing | Units overlap or clip | Medium |
| Incorrect gate calculation | 1. Pass multiple gates quickly | Correct unit calculation | Wrong unit count displayed | High |
| Jump pad make unit fall on each other | 1. Stack a large crowd<br>2. Step on Jump pad | All units land and stand on the ground correctly | Some units stand on top of each other when landing | Low |

---

## 4. Edge Cases

| Case | What happens | Result |
| --- | --- | --- |
| Pass through two gates quickly | Player hits gates in rapid succession | FAIL – Calculation inconsistency |
| Rapid movement left/right | Shake input quickly | FAIL – Crowd formation breaks |

---

##
