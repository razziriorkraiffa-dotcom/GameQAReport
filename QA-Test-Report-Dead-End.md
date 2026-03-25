# QA Test Report Dead End

## 1. Overview

**Dead End** is a retro-style low poly horror game where the player takes the role of a serial killer in a trailer park environment.

The objective is to collect 6 cereal items and eliminate 6 NPCs while progressing through the area. As the player completes objectives, supernatural apparitions begin to appear, increasing tension.

After completing all objectives, a final monster is triggered and kills the player, ending the game.

Testing focuses on core gameplay systems including player interaction, kill mechanics, item collection, event triggers, enemy spawning, and overall game flow. Edge cases and trigger consistency are also evaluated.

---

## 2. Test Cases

| ID | Test Case | Steps | Expected | Result |
| --- | --- | --- | --- | --- |
| DE01 | Player movement | Use WASD to move | Player moves correctly | OK |
| DE02 | Camera control | Move mouse | Camera rotates properly | OK |
| DE03 | Collect cereal | Move to cereal | Cereal disappears, counter +1 | OK |
| DE04 | Kill NPC | Approach NPC and trigger kill | NPC dies, kill count +1 | OK |
| DE05 | Multiple kills progression | Kill several NPCs | Apparitions begin to appear | OK |
| DE06 | Apparition spawn trigger | Reach mid progress (3 kills) | Apparitions spawn correctly | OK |
| DE07 | Kill all NPCs | Kill all 6 NPCs | Objective complete | OK |
| DE08 | Collect all cereals | Collect all 6 cereals | Objective complete | OK |
| DE09 | Final monster trigger | Complete all objectives | Monster spawns and attacks player | OK |
| DE10 | Player death (ending) | Let final monster reach player | Player dies, game ends | OK |

---

## 3. Bug Reports

| Title | Steps | Expected | Actual | Severity |
| --- | --- | --- | --- | --- |
| Movement stuck at sewage area | 1. Go down the drainage in the middle of the map | Can jump back normally | Sometimes get stuck in the drainage and require jumping repeatedly at the right angle to escape | Low |
| Player stuck at doorstep | 1. Move to any house<br>2. Open door | Door opens normally | Door collider pushes player back and sometimes causes player to get stuck at balcony | Medium |

---

## 4. Edge Cases

| Case | What happens | Result |
| --- | --- | --- |
| Spin camera fast when trigger the apparition | Camera spins around endlessly until the event is over | FAIL – Visual Glitch / Missed event |

---

##
