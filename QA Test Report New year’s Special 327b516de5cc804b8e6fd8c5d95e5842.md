# QA Test Report New year’s Special

## 1. Overview

**New Year’s Special** is a 2D Retro Line style platformer where the player navigates through levels featuring various mechanics such as enemy AI, environmental hazards, and movement challenges.

The gameplay includes chasing enemies, hiding mechanics, falling icicles, moving and collapsing platforms, slippery ice surfaces, and both flying and ground enemies.

The final stage features a boss encounter where enemies spawn dynamically. After defeating all enemies, platforms appear to guide the player to the endgame area, followed by a fireworks sequence.

Testing focuses on player controls, environmental interactions, enemy behavior, event triggers, and overall gameplay flow, including edge cases and system stability.

---

## 2. Test Cases

| ID | Test Case | Steps | Expected | Result |
| --- | --- | --- | --- | --- |
| NY01 | Player movement | Move left/right, jump | Player moves and jumps correctly | OK |
| NY02 | Enemy chase behavior | Enter enemy range | Enemy follows player | OK |
| NY03 | Falling icicle | Stand under icicle | Icicle falls and damages player | OK |
| NY04 | Moving platform | Stand on platform (A → B) | Player moves with platform | OK |
| NY05 | Falling platform | Stand on platform | Platform falls after delay | OK |
| NY06 | Slippery ice | Move on ice surface | Reduced friction, sliding effect | OK |
| NY07 | Boss room spawn | Enter boss area | Enemies spawn correctly | FAIL – Enemy spawn in wrong spot |

---

## 3. Bug Reports

| Title | Steps | Expected | Actual | Severity |
| --- | --- | --- | --- | --- |
| Icicle collision inconsistency | 1. Stand at edge of icicle zone | Player takes damage | No damage or delayed hit | Medium |
| Player stuck underground | Jumping and running at any normal platform | Player move around and landed normally | Sometimes player glitch through the ground and stuck underground. | High |
| Jumping animation glitch | Jump and land repeatedly | Player change from jumping animation to walking animation smoothly and normally | Sometimes player stuck in jumping animation while walking on the ground | Medium |

---

## 4. Edge Cases

| Case | What happens | Result |
| --- | --- | --- |
| Jump onto moving platform edge | Player lands at edge | FAIL – Player slips or falls unexpectedly |
| Move between ice and normal ground rapidly | Switch surfaces quickly | FAIL – Movement feels inconsistent |
| Enemy + icicle overlap | Enemy and hazard trigger together | FAIL – Damage or behavior conflict |

---

##