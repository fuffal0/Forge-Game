# Forge Master - Development TODO List

## 📋 Overview
This document tracks all planned features and improvements for Forge Master based on mobile tycoon game best practices.

---

## ✅ COMPLETED FEATURES

### **Achievement System** ✓
- [x] 40+ achievements across 8 categories
- [x] Achievement progress bar (X/Y unlocked with %)
- [x] Chapter system (5 chapters with goals)
- [x] Reward system (gold + XP)
- [x] Visual unlock states (locked/unlocked)
- [x] Integration with all game systems
- [x] Achievements tab UI

**Completed:** December 2024

### **Quest/Mission System** ✓
- [x] Quest data structure (early/mid/late game pools)
- [x] Quest tracking UI (sidebar panel with progress bar)
- [x] Active quest display showing current objective
- [x] Quest types: Craft, Sell, Gold, Rarity, Materials, Upgrades, Rivals, Weapon-specific
- [x] Quest rewards (gold + XP)
- [x] Quest completion celebrations
- [x] Auto-generate next quest on completion
- [x] Quest completion counter

**Completed:** December 2024

---

## 🎯 PHASE 1 - RETENTION (Week 1-2)
**Goal:** Give players immediate goals and show progression clearly

### 1.1 Quest/Mission System ✅
**Priority:** CRITICAL - **COMPLETED**
**Description:** Add a quest system that gives players immediate objectives
**Features:**
- [x] Create quest data structure
- [x] Quest tracking UI (sidebar or dedicated panel)
- [x] Active quest display showing current objective
- [x] Quest types:
  - [x] Craft X weapons
  - [x] Sell Y items
  - [x] Reach Z gold
  - [x] Achieve specific rarity
  - [x] Defeat a rival
  - [x] Craft specific weapon types
  - [x] Purchase upgrades
  - [x] Accumulate materials
  - [x] Gain reputation
- [x] Quest rewards (gold, XP, materials)
- [x] Quest completion celebrations
- [x] Auto-generate next quest on completion
- [x] Quest completion counter (shows total completed)

**Implementation Details:**
- 3 quest pools: Early (Level 1-5), Mid (Level 6-15), Late (Level 16+)
- Dynamic quest generation with random values
- Progress tracking integrated into all game systems
- Visual progress bar with percentage
- Automatic quest creation after 2-second delay
- Quest panel appears in status area with blue border

**Completed:** December 15, 2024

---

### 1.2 Progress Bars (XP, Reputation, Upgrades) ❌
**Priority:** HIGH
**Description:** Show visual progress toward next milestones

**Features:**
- [ ] XP progress bar to next level
  - [ ] Show "X / Y XP" with percentage
  - [ ] Visual bar that fills up
  - [ ] Placed near level display
  
- [ ] Reputation progress bar to next rank
  - [ ] Show "X / Y Rep to [Next Rank]"
  - [ ] Visual progress indication
  - [ ] Celebrate rank changes
  
- [ ] Upgrade unlock previews
  - [ ] Gray out locked upgrades
  - [ ] Show "Unlocks at X gold" or "Requires level Y"
  - [ ] Preview upgrade benefits before purchasing

**UI Changes:**
```
Level 5 ████████░░░░ 850/1,200 XP to Level 6

Reputation ██████░░░░ 1,200/2,000 to Renowned Blacksmith

[Locked Upgrade]
Master's Hammer - Requires 500 gold
Effect: +15% weapon value
```

---

### 1.3 Phased Feature Unlocking ❌
**Priority:** MEDIUM
**Description:** Don't overwhelm new players - unlock features gradually

**Unlock Schedule:**
- [ ] **Start (Level 1)**: Only Craft, Shop, Buy Materials tabs visible
- [ ] **Level 2**: Unlock Stats tab + tutorial message
- [ ] **Level 3**: Unlock Buy Materials tab (Steel+)
- [ ] **Level 5**: Unlock Gear tab + Upgrades tab
- [ ] **Level 7**: Unlock Services tab
- [ ] **Level 10**: Unlock Notice Board tab
- [ ] **Level 12**: Unlock Market Intelligence tab
- [ ] **First rival appears**: Tutorial message about competition

**Implementation:**
- [ ] Tab visibility based on level
- [ ] Unlock notification messages
- [ ] Tutorial tooltips for new features
- [ ] Save unlock state

---

### 1.4 Unlock Previews ❌
**Priority:** MEDIUM
**Description:** Show what's coming next to motivate players

**Features:**
- [ ] Show locked upgrades with requirements
- [ ] Display next material unlock and cost
- [ ] Preview next rank requirements
- [ ] Show locked achievements (already done ✓)
- [ ] "Coming at Level X" indicators

---

## 🔧 PHASE 2 - DEPTH (Week 3-4)
**Goal:** Make unused stats functional and add gameplay depth

### 2.1 Implement Unused Stats ❌
**Priority:** HIGH
**Description:** Make Efficiency, Speed, and Business stats actually work

#### Efficiency Stat
- [ ] Each point = 1% chance to not consume materials
- [ ] Visual feedback when materials are saved
- [ ] Update crafting function to check efficiency
- [ ] Show efficiency % in stats tab

**Example:** 5 Efficiency = 5% chance to craft for free

#### Speed Stat
- [ ] Each point = 2% faster crafting time
- [ ] Show actual time reduction
- [ ] Display crafting timer (optional)
- [ ] Update time calculation function

**Example:** 10 Speed = 20% faster crafting

#### Business Stat
- [ ] Each point = 2% higher customer budgets
- [ ] Show budget increase in customer display
- [ ] Update customer generation function
- [ ] Display business bonus in stats

**Example:** 5 Business = +10% customer budgets (100g → 110g)

---

### 2.2 Implement Gear Stat Bonuses ❌
**Priority:** MEDIUM
**Description:** Make non-luck gear perks actually work

**Gear Perks to Implement:**
- [ ] Gold Find % → Bonus gold on sales
- [ ] XP Bonus % → Faster leveling
- [ ] Efficiency % → Stack with efficiency stat
- [ ] Speed % → Stack with speed stat
- [ ] Business % → Stack with business stat
- [ ] Smithing → Stack with smithing stat (already partially works)

**Implementation:**
- [ ] Update getEffectiveStats() or create new helper
- [ ] Apply bonuses in relevant calculations
- [ ] Show gear bonuses in stats display
- [ ] Visual indicator when bonuses apply

---

### 2.3 Add Crafting Timer Visualization ⚠️
**Priority:** LOW
**Description:** Show crafting progress to make time meaningful

**Features:**
- [ ] Progress bar during crafting
- [ ] Time remaining display (e.g., "3.2s remaining")
- [ ] Optional: Animation during craft
- [ ] Speed stat bonus visible in timer

**UI:**
```
Crafting... ████████░░ 2.4s remaining
(Speed bonus: -20%)
```

---

### 2.4 Batch Crafting Option ❌
**Priority:** MEDIUM
**Description:** Allow crafting multiple items at once

**Features:**
- [ ] "Craft X" button with quantity selector
- [ ] Discount for bulk crafting (5-10% material savings)
- [ ] Shows total time and total cost
- [ ] Option for 1/5/10/max quantities
- [ ] Batch completes all at once (or one-by-one?)

**UI:**
```
Iron Sword
[Craft 1] [Craft 5] [Craft 10] [Craft Max]

Craft 5: Requires 15 iron, takes 12s total
```

---

## 🎨 PHASE 3 - VARIETY (Week 5-6)
**Goal:** Add alternative gameplay loops and activities

### 3.1 Special Order System ❌
**Priority:** HIGH
**Description:** Time-limited high-stakes crafting requests

**Features:**
- [ ] Special orders appear randomly (every 15-30 mins)
- [ ] Requirements: Specific weapon type + minimum rarity
- [ ] Time limit (5-15 minutes)
- [ ] Higher rewards than normal sales
- [ ] Reputation penalty for failure/timeout
- [ ] Visual indicator for active special order
- [ ] Sound/notification when order appears

**Example:**
```
🎯 SPECIAL ORDER
Lord Blackwood requests an Epic Greatsword
Time Remaining: 8:45
Reward: 500g + 100 rep
Failure: -50 rep
```

---

### 3.2 Material Expedition Mechanic ❌
**Priority:** MEDIUM
**Description:** Send apprentice on trips to gather materials

**Features:**
- [ ] Click to send apprentice on expedition
- [ ] Choose expedition type (Iron/Steel/Silver/etc.)
- [ ] Costs gold upfront (investment)
- [ ] Takes real time (5-15 minutes)
- [ ] Returns with materials (or fails)
- [ ] Risk/reward scaling with material tier
- [ ] Can only have one expedition active
- [ ] Progress indicator and timer

**Example:**
```
EXPEDITIONS
[Send Apprentice]

Silver Mine Expedition
Cost: 100g | Duration: 10 mins
Potential Reward: 5-15 silver
Risk: 30% chance of failure
```

---

### 3.3 Achievement/Badge Collection System ✓
**Priority:** COMPLETED
**Status:** Already implemented with 40+ achievements

---

### 3.4 Daily Login Bonuses ❌
**Priority:** MEDIUM
**Description:** Reward players for returning each day

**Features:**
- [ ] Track last login date
- [ ] Daily reward on first login each day
- [ ] Escalating rewards (day 1, 2, 3... up to day 7)
- [ ] Reset after 7 days or continue
- [ ] Rewards: gold, materials, XP, gear pieces
- [ ] Visual calendar showing streak
- [ ] Notification on login

**Example:**
```
DAILY LOGIN BONUS
Day 3 Reward: 100 gold + 5 steel
Login Streak: 3 days
Next Reward: 150 gold + Iron Sword
```

---

### 3.5 Smithing Competitions ❌
**Priority:** LOW
**Description:** Weekly challenges against AI

**Features:**
- [ ] Weekly competition starts automatically
- [ ] Challenge: Craft best weapon in category
- [ ] Compete against procedural AI entries
- [ ] Judged on quality score + rarity
- [ ] Rewards: Prestige points, gold, reputation
- [ ] Competition history/trophy display
- [ ] Different categories each week

**Example:**
```
WEEKLY COMPETITION: Best Greatsword
Entries close in: 2 days, 14 hours

Your Best: Epic Flame Greatsword (87 quality)
Current Leader: Legendary Storm Blade (94 quality)

1st Place: 1000g + 500 rep + Gold Trophy
```

---

## 🎭 PHASE 4 - POLISH (Week 7+)
**Goal:** Improve feel, add juice, refine experience

### 4.1 Tutorial System ❌
**Priority:** MEDIUM
**Description:** Guide new players through first steps

**Features:**
- [ ] First-time tutorial sequence
- [ ] Step-by-step instructions
- [ ] Highlight UI elements
- [ ] Force first actions (craft first weapon, sell it)
- [ ] Optional: Tooltip system (hover for help)
- [ ] Can be skipped by experienced players
- [ ] Tutorial progress saved

**Tutorial Flow:**
1. Welcome message
2. "Buy 5 iron" (forced)
3. "Craft an iron sword" (forced)
4. "Wait for customer"
5. "Sell your weapon"
6. "Allocate stat points"
7. Tutorial complete!

---

### 4.2 Sound Effects ❌
**Priority:** LOW
**Description:** Audio feedback for actions

**Sounds Needed:**
- [ ] Hammer strike (crafting)
- [ ] Success chime (craft success)
- [ ] Failure clang (craft failure)
- [ ] Coin drop (sale)
- [ ] Level up fanfare
- [ ] Achievement unlock
- [ ] Customer enters shop
- [ ] Button clicks

**Implementation:**
- [ ] Use Web Audio API
- [ ] Volume control in settings
- [ ] Mute option
- [ ] Sound toggle saved to localStorage

---

### 4.3 Offline Progress ❌
**Priority:** MEDIUM
**Description:** Earn while away from game

**Features:**
- [ ] Track time offline
- [ ] Calculate passive earnings
- [ ] Maximum 8-12 hours of offline progress
- [ ] Show "While you were away" summary
- [ ] Reduced efficiency (50% of active play)
- [ ] Requires certain upgrades unlocked?

**Implementation:**
- [ ] Save last active timestamp
- [ ] On load, check time difference
- [ ] Simulate reduced crafting/selling
- [ ] Award accumulated gold/XP/rep
- [ ] Display summary modal

**Example:**
```
WELCOME BACK!
You were away for 4 hours

While you were gone:
- Crafted 12 weapons
- Earned 850 gold
- Gained 300 reputation
- Leveled up! (x1)
```

---

### 4.4 Prestige/New Game+ System ❌
**Priority:** LOW
**Description:** Endgame loop for replayability

**Features:**
- [ ] Prestige option after reaching victory (100k rep)
- [ ] Reset most progress but keep some bonuses
- [ ] Prestige currency/points
- [ ] Permanent bonuses (prestige upgrades)
- [ ] Prestige level display
- [ ] Special prestige-only achievements
- [ ] Faster progression on subsequent runs

**Prestige Bonuses Ideas:**
- Starting gold multiplier
- Starting materials bonus
- XP gain boost
- Rare unlock earlier materials
- Start at higher level

**Example:**
```
PRESTIGE AVAILABLE
Reset your forge to gain permanent bonuses!

You will keep:
- Achievements
- Prestige level (+1)
- Prestige upgrades

You will lose:
- Gold, reputation, level
- Weapons, gear, materials
- Rivals, customers

Prestige Bonus: +50% starting gold
```

---

## 🔮 FUTURE IDEAS (Not Prioritized)

### Additional Features to Consider:
- [ ] **Seasonal Events**: Limited-time events with unique rewards
- [ ] **Cosmetic System**: Customize forge appearance
- [ ] **Recipe Discovery**: Find rare weapon blueprints
- [ ] **Assistant/Helper NPCs**: Hire workers with unique bonuses
- [ ] **Crafting Minigames**: Optional skill-based bonuses
- [ ] **Weapon Enchanting**: Add magical properties post-craft
- [ ] **Guild System**: Join/create guilds for group benefits
- [ ] **Leaderboards**: Compare with other players (requires backend)
- [ ] **Trading System**: Trade with other players or NPCs
- [ ] **Story Mode**: Narrative quests and character development
- [ ] **Random Encounters**: Traveling merchants, thieves, etc.
- [ ] **Weather System**: Affects customer traffic or material costs
- [ ] **Reputation Tiers**: Unlock special customers at high rep
- [ ] **Crafting Specializations**: Become expert in certain weapon types

---

## 📊 PRIORITY SUMMARY

### **Must-Have (Before Public Release):**
1. Quest/Mission System (Phase 1.1)
2. Progress Bars for XP/Rep (Phase 1.2)
3. Implement Unused Stats (Phase 2.1)
4. Phased Feature Unlocking (Phase 1.3)

### **Should-Have (Early Updates):**
1. Special Orders (Phase 3.1)
2. Gear Stat Bonuses (Phase 2.2)
3. Daily Login Bonuses (Phase 3.4)
4. Tutorial System (Phase 4.1)

### **Nice-to-Have (Polish):**
1. Batch Crafting (Phase 2.4)
2. Material Expeditions (Phase 3.2)
3. Offline Progress (Phase 4.3)
4. Sound Effects (Phase 4.2)

### **Long-Term (Post-Launch):**
1. Prestige System (Phase 4.4)
2. Smithing Competitions (Phase 3.5)
3. Future ideas as appropriate

---

## 📝 NOTES

### Design Principles to Maintain:
- **Discovery-based learning** - Keep tooltips optional
- **Hidden mechanics** - Preserve luck mystery
- **Replayability** - Randomization is key
- **Merit-based** - No pay-to-win
- **Recovery possible** - No permanent failure
- **Single-player focus** - Don't require online features

### Technical Considerations:
- Keep localStorage saves compatible across updates
- Add version migration for new features
- Maintain performance with new systems
- Test on mobile browsers (touch support)
- Consider file size (keep under 500KB if possible)

### Balancing Notes:
- Don't make progression too fast with new features
- Ensure achievements remain challenging but achievable
- Keep quest rewards balanced with existing economy
- Test offline progress rates carefully

---

## 🎯 CURRENT STATUS

**Latest Update:** December 15, 2024
**Version:** 1.2 (with Achievements + Quests)
**Next Priority:** Phase 1.2 - Progress Bars (XP, Reputation, Upgrades)

**Active Development:**
- Working on: Quest/Mission system (COMPLETED ✓)
- Next up: Progress bars for XP and Reputation
- Backlog: Stat implementation, phased unlocking

**Recently Completed:**
1. Achievement System (40+ achievements, 8 categories)
2. Quest/Mission System (dynamic quests with 9 quest types)

---

*Last Updated: December 15, 2024*
