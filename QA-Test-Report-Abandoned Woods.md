# QA Test Report Abandoned Woods

## 1. Overview

A first-person horror game where the player collects 8 skulls while avoiding a monster that moves only when not observed.

Testing focuses on gameplay systems, enemy behavior, item collection, and win/lose conditions, along with edge case and stability testing.

---

## 2. Test Cases

| ID | Test Case | Steps | Expected | Result |
| --- | --- | --- | --- | --- |
| AW01 | Player movement | Use WASD to move | Player moves smoothly in all directions | OK |
| AW02 | Camera look | Move mouse | Camera rotates correctly | OK |
| AW03 | Collect skull | Move to skull and collide | Skull disappears, counter +1 | OK |
| AW04 | Collect all 8 skulls | Collect all skulls in map | Counter reaches 8, portal activates | OK |
| AW05 | Monster freeze mechanic | Look directly at monster | Monster stops moving | OK |
| AW06 | Monster movement | Look away from monster | Monster moves toward player | OK |
| AW07 | Player death | Let monster touch player | Death screen triggers | FAIL – Death sometimes not triggered on fast collision |
| AW08 | Escape through portal | Collect 8 skulls → enter portal | Game ends / win condition triggers | FAIL – Portal not triggering consistently |

---

## 3. Bug Reports

| Title | Steps | Expected | Actual | Severity |
| --- | --- | --- | --- | --- |
| Player not dying on contact | 1. Let monster approach<br>2. Stand still<br>3. Get touched | Player dies immediately | Player sometimes survives collision | High |
| Inconsistent Skull Interaction | 1. Move near skull<br>2. Observe UI prompt | “[E]” appears reliably | UI sometimes does not appear | Medium |
| Lag on first interaction | 1. Approach skull collider | No lag, UI appears instantly | Screen freezes 1–2 seconds | Medium |
| Monster stuck on obstacles | 1. Trigger monster<br>2. Move near tree while looking at monster | Monster navigates around obstacle | Monster clips or gets stuck in tree | High |

---

## 4. Edge Cases

| Case | What happens | Result |
| --- | --- | --- |
| Rapid camera flick (look on/off monster quickly) | Monster state switches rapidly | FAIL – Monster jitters / inconsistent movement |
| Collect skull while monster touching player | Two systems trigger at same time | FAIL – Game state conflict (no death / no collect) |
| Enter portal while monster chasing | Player reaches portal at same time as monster | OK – Game ends correctly |

---

##
