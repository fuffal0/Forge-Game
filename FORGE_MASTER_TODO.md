# Forge Master - Development Roadmap (Overgeared Vision)

## 🎯 Core Vision
Transform Forge Master from a **tycoon game** into a **crafting mastery simulator** inspired by the manhwa *Overgeared*. The focus shifts from fast progression to meaningful crafting experiences where each weapon tells a story of the smith's growing mastery.

---

## ✅ COMPLETED FEATURES (Phase 1 - Foundation)

### **Phase 1 - Retention & Progression Systems** ✓
**Completed:** December 16, 2024

1. [x] Achievement System (40+ achievements, 8 categories)
2. [x] Quest/Mission System (9 quest types, dynamic scaling)
3. [x] Progress Bars (XP, Reputation, Upgrade previews)
4. [x] Phased Feature Unlocking (7 unlock tiers)
5. [x] Options Menu (auto-save toggle)
6. [x] All quest types properly track progress
7. [x] Calendar system with fantasy seasons

**Status:** Foundation complete and stable. Ready for core redesign.

---

## 🔥 CRITICAL PATH - OVERGEARED TRANSFORMATION

This is the new priority order based on the Overgeared vision. Everything else is secondary.

---

## 📍 PHASE 2 - THE FORGING EXPERIENCE (CORE REDESIGN)
**Priority:** CRITICAL - Start Immediately
**Goal:** Transform crafting from transaction to experience

### 2.1 Forging Animation & Timer System ⚡ NEXT
**Description:** Every craft becomes a 3-5 second immersive experience

**Core Mechanics:**
- [ ] Remove instant crafting
- [ ] Add forging animation system (3-5 seconds per craft)
- [ ] Visual progress bar during forging
- [ ] Hammer strike animation/effects
- [ ] Material glow/spark effects
- [ ] Success/failure visual feedback
- [ ] Quality reveal ceremony

**Technical Implementation:**
- [ ] Create `startForging(weaponType, material)` function
- [ ] Forging state machine (preparing → heating → striking → cooling → reveal)
- [ ] Animation CSS keyframes
- [ ] Progress tracking during forge
- [ ] Interrupt/cancel handling
- [ ] Queue system (can't start new forge during active forge)

**UI Changes:**
```
[FORGING IN PROGRESS]
Iron Sword
████████░░░░ 60%
Time Remaining: 2.1s

[Hammer strikes rhythmically...]
Your focus is unwavering.
```

**Estimated Time:** 4-6 hours

---

### 2.2 Focus & Concentration System ⚡ HIGH PRIORITY
**Description:** Grid's mental state affects crafting - the core of Overgeared smithing

**Focus Points System:**
- [ ] Add Focus Points (FP) resource to gameState
- [ ] FP bar in UI (max 100, current amount)
- [ ] FP regeneration (1 per minute passively)
- [ ] FP consumption during crafting (10-30 FP per craft based on material)
- [ ] Low FP = worse results, High FP = better results
- [ ] "Exhausted" state when FP reaches 0

**Focus Affects:**
- [ ] Base quality multiplier (50 FP = 1.0x, 100 FP = 1.5x, 0 FP = 0.5x)
- [ ] Critical success chance (high focus = rare quality spikes)
- [ ] Failure rate (tired smith makes mistakes)
- [ ] Insight discovery chance

**UI Display:**
```
🧠 Focus: ████████░░ (80/100)
State: Concentrated

[Craft Iron Sword] (Costs 15 FP)
```

**Rest Mechanics:**
- [ ] "Take Break" button (recover 50 FP, costs 30 seconds game time)
- [ ] "Meditate" button (full FP recovery, costs 5 minutes game time)
- [ ] Auto-rest when FP below 20? (optional setting)

**Estimated Time:** 3-4 hours

---

### 2.3 Random Events During Forging 🎲
**Description:** Grid's breakthroughs, setbacks, and moments of inspiration

**Event Types:**

**Positive Events (15% chance total):**
- [ ] "Perfect Strike!" - Your hammer finds ideal rhythm (+10-15 quality)
- [ ] "Material Resonance" - The metal sings under your touch (+quality, +insight)
- [ ] "Moment of Clarity" - Flash of inspiration! (+20 quality, rare)
- [ ] "Steady Hands" - Your control is impeccable (guarantee no failure)
- [ ] "Flow State" - Time seems to slow... (unlock special option)

**Negative Events (10% chance total):**
- [ ] "Distraction" - Your focus wavers (-5 quality)
- [ ] "Impurity Found" - The material resists (-10 quality)
- [ ] "Timing Off" - Rhythm breaks (-quality, +failure chance)
- [ ] "Exhaustion Creeps In" - Your arms tire (lose extra FP)

**Neutral/Choice Events (5% chance):**
- [ ] "Experiment?" - Try something new? (Risk/Reward choice)
- [ ] "Perfect Moment" - Strike now for bonus! (Timing challenge)
- [ ] "Material Whispers" - Learn something about this material

**Implementation:**
- [ ] Event pool system (weighted random selection)
- [ ] Event messages display during forging animation
- [ ] Events affect quality calculation
- [ ] Some events affect hidden luck
- [ ] Track event history for statistics

**Display:**
```
[FORGING: 2.5s remaining]
████████░░░░

✨ Perfect Strike!
Your hammer finds the ideal rhythm.
The metal seems to respond to your will.

Quality Bonus: +12
```

**Estimated Time:** 4-5 hours

---

### 2.4 Crafting Insights & Discovery System 💡
**Description:** Permanent knowledge gained through experience - Grid's learning journey

**Insight Categories:**

**Material Insights:**
- [ ] "Iron's True Nature" - +5% quality on all iron crafts
- [ ] "Steel Requires Patience" - -5% fail rate on steel
- [ ] "Silver's Temperament" - Understand silver properties
- [ ] "Mithril Mysteries" - Unlock hidden mithril techniques
- [ ] "Adamantine Mastery" - Peak material understanding

**Technique Insights:**
- [ ] "Rapid Forging Method" - Craft 20% faster (quality tradeoff)
- [ ] "Perfect Temperature Control" - Better heat management
- [ ] "Hammer Weight Distribution" - Improved striking
- [ ] "Grain Alignment" - Reveal material structure
- [ ] "Soul Binding" - Impart extra quality to weapons

**Weapon Insights:**
- [ ] "Sword Balance Principles" - +quality on swords
- [ ] "Axe Head Density" - Better axes
- [ ] "Dagger Precision" - Sharper daggers
- [ ] (One for each weapon type)

**Discovery Mechanics:**
- [ ] Random chance during forging (1-5% based on conditions)
- [ ] Higher chance with high focus
- [ ] Higher chance on failures (learn from mistakes!)
- [ ] Higher chance when experimenting
- [ ] Certain level thresholds guarantee insights

**Insight Journal:**
- [ ] New tab: "Smithing Journal"
- [ ] Lists all discovered insights
- [ ] Shows locked insights as "???"
- [ ] Tracks how many times you've crafted each item
- [ ] Displays mastery level per material/weapon type

**UI:**
```
💡 INSIGHT DISCOVERED!

"Iron's True Nature"

Through countless forgings, you've come to 
understand iron's fundamental properties.
It is honest metal - what you put in, 
you get out.

Effect: +5% base quality on all Iron weapons
Discovered: After crafting 50 iron weapons
```

**Estimated Time:** 5-6 hours

---

### 2.5 Material Mastery & Attunement 🔬
**Description:** Deep understanding of materials through study and repetition

**Mastery System:**
- [ ] Each material has mastery level (0-100)
- [ ] Gain mastery XP every time you craft with material
- [ ] Higher mastery = better understanding = better results
- [ ] Mastery levels unlock benefits

**Mastery Benefits:**
```
Iron Mastery: 45/100 (Journeyman)

Benefits Unlocked:
✓ Level 10: +5% quality
✓ Level 25: -10% fail rate  
✓ Level 50: Rare insight: "Iron's Malleability"
  Level 75: ??? (Locked)
  Level 100: ??? (Master Rank)
```

**Study System:**
- [ ] "Study Material" button (costs gold, takes time)
- [ ] Focused study session (mini-game or time-gate)
- [ ] Grants mastery XP without crafting
- [ ] Reveals hidden material properties

**Material Properties (Hidden → Revealed):**
```
Iron (Mastery: 15)
Known Properties:
✓ Malleable when heated
✓ Prone to rust
? Reacts well to repeated strikes
? ???
? ???

[Study Iron] (50g, 2 minutes)
```

**Attunement:**
- [ ] "Attune to Material" action before crafting
- [ ] Costs time/focus but improves understanding
- [ ] Temporary bonus to next craft with that material
- [ ] "I need to understand this metal before I begin..."

**Estimated Time:** 4-5 hours

---

### 2.6 Active Crafting Moments (Timing Challenges) ⚡
**Description:** Player skill matters - Grid's perfect timing and precision

**Timing Challenges:**
- [ ] Random prompts during forging: "Strike NOW!"
- [ ] 0.5-1 second window to click/press key
- [ ] Success: +10-20 quality bonus
- [ ] Miss: -5 quality penalty
- [ ] Multiple successes: Combo multiplier!

**Perfect Rhythm System:**
```
[PERFECT!] +15 quality
[PERFECT!] +15 quality (2x COMBO!)
[PERFECT!] +15 quality (3x COMBO! - "You're in the zone!")

Miss: Combo broken
```

**Critical Moments:**
- [ ] "Final Strike" - Last chance for perfection
- [ ] "Quenching Point" - Perfect cooling timing
- [ ] "Tempering Window" - Precise temperature control

**Skill Expression:**
- [ ] Good players can achieve higher quality
- [ ] Bad timing = worse results (but still crafts)
- [ ] Optional: Can disable in settings for accessibility

**Visual Feedback:**
```
[FORGING: Iron Sword]
████████░░

!! STRIKE NOW !!
[Circle shrinks - click when small]

PERFECT! ⚡
The hammer connects flawlessly.
+18 Quality
```

**Estimated Time:** 3-4 hours

---

### 2.7 Quality Reveal Ceremony 🎊
**Description:** The moment of truth - what have you created?

**Reveal Sequence:**
- [ ] Forging completes → brief pause
- [ ] Weapon materializes with effect
- [ ] Rarity revealed with fanfare
- [ ] Quality score shown
- [ ] Perks displayed one by one
- [ ] Special message for high-quality items

**Rarity-Based Reveals:**
```
Poor/Common: Simple appear, quiet
Uncommon: Gentle glow, soft chime
Rare: Blue shimmer, clear chime
Epic: Purple aura, dramatic music
Legendary: Golden explosion, fanfare!
Mythic: Reality warps, legendary reveal!
```

**Special Messages:**
```
[Legendary Quality Achieved!]

"Ancient Mithril Greatsword"
★★★★★ LEGENDARY

You've poured your very soul into this blade.
It will be remembered for generations.

Quality: 94/100
Worth: 2,450 gold

[Your reputation grows...]
+500 Reputation
```

**Photo Mode:**
- [ ] "Admire Weapon" button after craft
- [ ] Rotatable 3D view (or detailed sprite)
- [ ] Weapon stats overlay
- [ ] Share/screenshot feature

**Estimated Time:** 3-4 hours

---

## 📍 PHASE 3 - MASTERY DEPTH
**Goal:** Long-term progression and replayability through mastery

### 3.1 Signature Techniques System
**Description:** Unlock and choose crafting approaches (Grid's style evolution)

**Technique Types:**
- [ ] Rapid Forging: 50% faster, -20% quality (quantity over quality)
- [ ] Careful Craftsmanship: 2x time, +30% quality (Grid's patient approach)
- [ ] Intuitive Smithing: ??? result, can be amazing or terrible (gamble)
- [ ] Meditative Forging: Requires full focus, exceptional quality
- [ ] Aggressive Striking: Higher variance, chance for breakthroughs
- [ ] Precise Calculation: Consistent results, less variance

**Unlocking Techniques:**
- [ ] Start with "Standard Forging"
- [ ] Level 5: Unlock "Rapid Forging"
- [ ] Level 10: Unlock "Careful Craftsmanship"
- [ ] Level 15: Unlock "Intuitive Smithing"
- [ ] Insights can unlock unique techniques
- [ ] Special quests unlock legendary techniques

**Selection:**
```
Choose Forging Technique:

○ Standard Forging
  Time: 3s | Quality: Normal

● Careful Craftsmanship 
  Time: 6s | Quality: +30%
  "Take your time. Do it right."

○ Rapid Forging
  Time: 1.5s | Quality: -20%
  "Speed is of the essence."

[Begin Forging]
```

**Estimated Time:** 4-5 hours

---

### 3.2 Weapon Mastery Progression
**Description:** Become a specialist or generalist

**Weapon Mastery Levels:**
- [ ] Track crafts per weapon type
- [ ] Mastery unlocks bonuses
- [ ] Title system (Novice → Master → Legendary)

```
SWORD MASTERY: Level 8 (Expert)
Crafted: 234 swords
Best Quality: 87/100 (Epic)

Bonuses:
✓ +10% sword quality
✓ -15% sword fail rate
✓ Insight: "Blade Balance"
  Next: Level 10 - "Sword Soul Binding"
```

**Specialization Path:**
- [ ] After 100 crafts of one type: "Specialize?"
- [ ] Specializing gives huge bonuses to that type
- [ ] Slight penalties to other types
- [ ] Can respec (expensive)

**Estimated Time:** 3-4 hours

---

### 3.3 Legendary Crafting Challenges
**Description:** Special crafting sessions for ultimate items

**Challenge Types:**
- [ ] Timed crafting: "Craft Epic+ in 10 minutes"
- [ ] Perfect run: "Craft 5 weapons without failure"
- [ ] Quality threshold: "Achieve 90+ quality score"
- [ ] Material restriction: "Craft Legendary using only Iron"

**Rewards:**
- [ ] Unique insights
- [ ] Special techniques
- [ ] Legendary materials
- [ ] Titles and achievements

**Weekly Competitions:**
- [ ] "Master Smith Challenge"
- [ ] Compete against AI rivals
- [ ] Submit your best weapon
- [ ] Rankings and rewards

**Estimated Time:** 5-6 hours

---

## 📍 PHASE 4 - IMMERSION & POLISH
**Goal:** Make it feel like Overgeared

### 4.1 Sound Design & Music
- [ ] Hammer striking sounds (multiple variations)
- [ ] Metal ringing/singing
- [ ] Fire crackling
- [ ] Success fanfares (rarity-based)
- [ ] Failure sounds (metal cracking)
- [ ] Background forge ambiance
- [ ] Focus/meditative music during crafting
- [ ] Epic music for legendary reveals

**Estimated Time:** 2-3 hours (using free assets)

---

### 4.2 Visual Effects & Particles
- [ ] Sparks flying during strikes
- [ ] Heat glow on metal
- [ ] Steam during quenching
- [ ] Rarity-based auras
- [ ] Quality shimmer effects
- [ ] Breakthrough flash effects
- [ ] Focus visualization

**Estimated Time:** 4-5 hours

---

### 4.3 Narrative Flavor Text
- [ ] Poetic descriptions during forging
- [ ] Grid-style internal monologue
- [ ] Dynamic text based on state
- [ ] Success/failure narration
- [ ] Weapon lore on hover

**Example:**
```
"The metal is honest. It will not lie to you.
Put in effort, receive results.
This is the way of the smith."

Your hammer rises and falls.
Each strike a conversation with the steel.
Today, it answers kindly.
```

**Estimated Time:** 3-4 hours

---

### 4.4 Smithing Journal & Statistics
- [ ] Personal crafting history
- [ ] Best weapons hall of fame
- [ ] Insights discovered
- [ ] Materials mastered
- [ ] Techniques learned
- [ ] Total strikes counted
- [ ] Perfect timings achieved
- [ ] Legendary moments logged

**Estimated Time:** 3-4 hours

---

## 📍 PHASE 5 - ADAPTED FEATURES (From Old Roadmap)

These features need to be reconsidered in light of the crafting focus:

### 5.1 Batch Crafting → **REMOVE or REDESIGN**
**Issue:** Contradicts the "every craft matters" philosophy
**Options:**
- Remove entirely (each craft is special)
- Redesign as "Training Mode" (practice, no items produced)
- "Mass Production" technique (much lower quality, for basic orders)

### 5.2 Offline Progress → **REDESIGN**
**Issue:** Can't auto-craft complex system
**Options:**
- Apprentice crafts basic items while away
- Gather insights/mastery passively
- Study materials offline
- NO offline crafting of important items

### 5.3 Special Orders → **KEEP & ENHANCE**
- Perfect fit for the vision!
- "Craft a Legendary sword in 10 minutes for the Duke"
- High stakes, high focus crafting
- Story moments through orders

### 5.4 Material Expeditions → **KEEP**
- Fits the world-building
- Rare material acquisition
- Adds strategic layer

### 5.5 Stat Implementation → **REDESIGN**
**Efficiency**: Reduce Focus cost per craft
**Speed**: Slightly faster forging (not too fast!)
**Business**: Better prices (unchanged)
**Smithing**: More focus during forge, higher quality ceiling

---

## 🎯 NEW PRIORITY ORDER

### **Immediate (This Week):**
1. Forging Animation & Timer (2.1) - FOUNDATION
2. Focus System (2.2) - CORE MECHANIC
3. Random Events (2.3) - ADDS VARIETY

### **Short Term (Next 2 Weeks):**
4. Insights & Discovery (2.4) - PROGRESSION
5. Material Mastery (2.5) - DEPTH
6. Active Moments (2.6) - SKILL EXPRESSION
7. Quality Reveal (2.7) - SATISFACTION

### **Medium Term (Month 2):**
8. Signature Techniques (3.1)
9. Weapon Mastery (3.2)
10. Sound & Music (4.1)
11. Visual Effects (4.2)

### **Long Term (Month 3+):**
12. Legendary Challenges (3.3)
13. Narrative Flavor (4.3)
14. Journal System (4.4)
15. Adapt remaining features (Phase 5)

---

## 🔄 CONVERSION TO HYBRID (Option B) - IF NEEDED

If full immersion becomes tedious, here's the pivot plan:

### **Fast Track to Hybrid:**
1. Keep all systems from Phase 2-3
2. Add "Quick Craft" button
   - Uses average of your past 10 crafts
   - No animation, instant
   - Costs no Focus
   - Lower quality ceiling
3. Add "Master Craft" button
   - Full Overgeared experience
   - Costs 50 Focus
   - Best quality potential
   - All the immersion
4. Let players choose per craft

**Implementation Time:** 2-3 hours (if systems already built)

---

## 📊 ESTIMATED TOTAL TIME

**Phase 2 (Core Transformation):** 25-35 hours
**Phase 3 (Mastery Depth):** 12-15 hours
**Phase 4 (Polish):** 12-16 hours
**Phase 5 (Adaptation):** 8-12 hours

**TOTAL:** 57-78 hours of development

---

## 💭 DESIGN PHILOSOPHY SHIFT

### **OLD Philosophy (Tycoon):**
- Fast progression
- Volume of crafts
- Economic optimization
- Strategic timing

### **NEW Philosophy (Overgeared):**
- Meaningful crafting
- Quality over quantity  
- Mastery through focus
- Discovery through experience

### **What Stays:**
- Hidden luck system
- Risk/reward (failure)
- Progression systems
- Rival competition
- World events

### **What Changes:**
- Crafting is now the CORE experience
- Each weapon has a story
- Player skill matters (timing)
- Knowledge is power (insights)

---

## 🎮 PLAYER EXPERIENCE TRANSFORMATION

### **Before (Tycoon Mode):**
```
1. Click craft → Roll dice → Get weapon
2. Repeat 100 times
3. Focus on economy, timing, optimization
```

### **After (Overgeared Mode):**
```
1. Choose technique, prepare mentally
2. Enter forging sequence (5 seconds)
3. Respond to events, hit perfect timings
4. Moment of truth - reveal the weapon
5. Feel pride in your creation
6. Learn and improve from experience
```

---

## 🔮 FUTURE VISION (Post-Launch)

If Option A succeeds, future additions:
- [ ] Weapon enchanting (add magic properties)
- [ ] Apprentice system (teach others your techniques)
- [ ] Legendary weapon questlines
- [ ] Multiplayer competitions
- [ ] Custom weapon orders with requirements
- [ ] Master smith tournaments
- [ ] Weapon soul binding (permanent upgrades)

---

## ⚠️ CRITICAL NOTES

1. **Playtesting is ESSENTIAL** - We need to verify the 3-5s timing isn't tedious
2. **Balance is key** - Focus regeneration must feel right
3. **Feedback loops** - Players must see improvement from mastery
4. **Accessibility** - Timing challenges should be optional
5. **Respect player time** - Even with immersion, avoid unnecessary waits

---

## 📝 CONVERSION PLAN (A → B)

If we need to switch to Hybrid (Option B):

**What to Keep:**
- All the systems (Focus, Insights, Mastery, Events)
- All the progression mechanics
- All the visual polish

**What to Add:**
- "Quick Craft" mode for routine work
- "Master Craft" mode for important pieces
- Player chooses which mode per craft
- Focus becomes the gate (Master Craft costs Focus)

**Changes Required:** Minimal (2-3 hours)
**Philosophy:** Grid also has routine days and legendary days

---

*Last Updated: December 16, 2024*
*Vision: Capture the soul of Overgeared's crafting mastery*
*Status: Phase 1 Complete, Phase 2 Ready to Begin*