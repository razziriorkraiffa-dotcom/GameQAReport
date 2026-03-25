# QA Test Report Stack Ball

## 1. Overview

**Stack Ball Clone** is a hyper-casual arcade game where the player controls a ball smashing through stacked platforms while avoiding forbidden surfaces.

The objective is to reach the bottom by breaking valid layers while avoiding obstacles that cause failure.

The game focuses on fast-paced gameplay, responsiveness, and quick retry loops.

Testing focuses on input responsiveness, collision detection, fail conditions, level progression, and overall gameplay loop stability.

---

## 2. Test Cases

| ID | Test Case | Steps | Expected | Result |
| --- | --- | --- | --- | --- |
| SB01 | Ball drop | Tap/hold input | Ball falls downward | OK |
| SB02 | Break valid platform | Hit breakable layer | Platform breaks | OK |
| SB03 | Hit forbidden platform | Hit non-breakable layer | Player fails | OK |
| SB04 | Continuous smash | Hold input through multiple layers | Ball breaks multiple layers smoothly | OK |
| SB05 | Input release | Release input mid-fall | Ball stops smashing | OK |
| SB06 | Level completion | Reach bottom | Next level or win triggers | OK |
| SB07 | Restart after fail | Fail → restart | Level resets correctly | OK |

---

## 3. Bug Reports

| Title | Steps | Expected | Actual | Severity |
| --- | --- | --- | --- | --- |
| Input delay | Tap repeatedly | Immediate response | Slight delay in ball action | Medium |
| UI misplaced | Purposely hit forbidden platform | Game over UI appear, all texts on screen is placed perfectly | Score of the run and Best score overlapped with Game Over text | Medium |
| Level does not reset after player die | play to level 2 and die purposely | Level reset to 1 | Level does not reset | High |

---

## 4. Edge Cases

| Case | What happens | Result |
| --- | --- | --- |
| Rapid tap spam | Tap very fast repeatedly | FAIL – Input inconsistency |

---

##