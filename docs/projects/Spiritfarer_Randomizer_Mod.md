# 🎲 Spiritfarer Randomizer Mod

Spiritfarer is one of the games I consider to be my favorites. This is a story driven game about replacing Charon and helping lost souls find their way on the Styx.
I've always wanted to replay it, have a new experience with this game. But it's really not meant to be replayed. Normally I solve this issue by playing a randomizer, but this game didn't have any. So I decided I would build it myself. 

**Role:** _Solo modder_ <br>
**Team size:** _soloe_ <br>
**Duration:** _2 months, ongoing_ <br>
**Tools:** _dnSpy, BepInEx, Visual Studio, C#_ <br>
**Links:** [Video](#videos)

## Overview

A story-driven game with few dedicated progression items doesn't exactly fit the "easy" category for a randomizer, so the first step was figuring out what could actually be randomized. Spiritfarer's progression ties to two things: spirits, and the Everlight (Stella's set of powers, like double jump or glide).

- **Spirits**: Each unlocks a minigame that yields materials, and often trigger progression events (like a new mailbox letter or a set of missions).
- **The Everlight**: The most direct progression — double jump reaches higher ledges, and so on for each ability.

Randomizing spirit order risked breaking story flow and progression logic, leading to bugs or softlocks, so I left it untouched, at least for now. The Everlight only has 7 upgrades, meaning even shuffled, it'd barely feel different from the base game. So I turned to a third progression layer instead: **islands**. You travel the Styx from island to island to meet characters, unlock upgrades, and complete missions and I had two ways to randomize that:

- **Boat upgrades**: Unlock new areas (e.g. an ice crusher up north, a fog light out east).
- **Island loading zones**: Islands sit outside the main world (the boat), reached only through loading zones, meaning they can be shuffled and their zones swapped.

With only 3 boat upgrades gating new areas, loading zones were the clearly stronger option. <br><br>

The mod is currently in R&D. Using **dnSpy** to decompile the game, I identified how islands load and how Everlight abilities are granted, then used **BepInEx** to patch those methods and alter their behavior. At this point, the mod can shuffle both island loading zones and Everlight upgrades.

The next challenge was surfacing these changes clearly to the player. Loading-zone shuffles are somewhat self-evident, but I wanted the map itself to reflect the new layout — both for novelty, and so players wouldn't need to take notes on where each zone now leads. I also wanted the Everlight UI to show the randomized ability instead of the base game's. This step proved harder than expected, and so far only the map display is complete. <br><br>

After this UI phase, I'll focus on the randomizer's core logic — the rules ensuring the game stays beatable despite shuffled progression. This will likely be the hardest part, requiring a thorough analysis of what each island and ability requires to unlock, and it comes last since it demands extensive playtesting. <br><br>

**To sum up:** islands and Everlight abilities can currently be shuffled, with loading zones already reflected on the map (ability UI still pending). Next up is the randomization logic itself. Here's the current roadmap:

- ✅ Modify the log system so that mod and game logs are visible during testing
- ✅ Create a json file with every Island, their name, and loading path in-game
- ✅ Add a randomization method to shuffle items with each other
- ✅ Patch the loading zone method to comply with the shuffled list
- ✅ Create a json file of all abilities and the flag associatied in-game
- ✅ Patch the Ability flag trigger to comply with the shuffled list
- ✅ Display the new loading zones on the map
- [ ] Display the new ability granted in the relevant UI canvas
- [ ] List all randomized loading zone and their required boat upgrades
- [ ] List all story progression islands and their needed abilities
- [ ] Establish the order in which progression islands must be visited to ensure proper story progress
- [ ] Implement randomization order to apply logic to the randomizer (Detailed tasks are still to be dertermined)


## Images & Videos

Hi, this page is still under construction 🏗️ ! I'm currently working on a video to showcase the current progress of the randomizer.

## Challenges & what I learned

- **Reverse engineering an unfamiliar codebase.** Working without source access meant relying entirely on dnSpy to map out how islands and abilities were structured. This is a slower, more methodical process than working in an engine I fully control, but it taught me to navigate and reason about other people's code with much less context than I'm used to.
- **Designing feedback for changes the player can't see coming.** A working randomizer isn't enough if players can't tell what changed. Figuring out how to display shuffled content clearly was an entirely different challenge than patching method for gameplay logic. It required a better understanding of Unity canvas system and the way that the devs put the map together. 
- **Planning for a challenge I haven't solved yet.** The randomization logic (keeping the game beatable no matter how progression is shuffled) is still ahead of me, and scoping it honestly (rather than underestimating it) has already been a useful exercise in project planning.

<div class="pagination" markdown>
  [1](Full_Plastic_Shooter.md) · 
  [2](Chasm.md) · 
  [3](Ijiraaq.md) · 
  [4](SNCF_SeriousGame.md) · 
  <span class="pagination__link pagination__link--current">5</span>
</div>
