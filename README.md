# ⚒️ Forge Master - Blacksmith Tycoon

A text-based blacksmith simulation game where you start with a humble forge and work your way to becoming the Blacksmith of Legend.

**Live Demo**: https://fuffal0.github.io/Forge-Game/forge_master.html

## 🎮 Game Overview

Forge Master is a deep, replayable browser-based game that combines crafting, economy management, and strategic decision-making. Each playthrough offers a unique experience through procedurally generated content, random events, and hidden mechanics that reward attentive players.

## ✨ Features

### Core Gameplay
- **Procedural Crafting System**: 7 rarity tiers (Poor → Mythic) with dynamic quality calculations
- **25+ Weapon Perks**: Randomly assigned based on item rarity
- **Risk-Based Crafting**: Material quality affects failure rates - failed crafts lose all materials
- **6 Weapon Types**: Dagger, Sword, Battle Axe, Mace, Greatsword, Warhammer
- **5 Material Tiers**: Iron → Steel → Silver → Mithril → Adamantine

### Progression Systems
- **Achievement System**: 40+ achievements across 8 categories
  - **Categories**: Crafting, Rarity, Sales, Wealth, Progression, Competition, Materials, Special
  - Visual progress tracking with completion percentage
  - Gold and XP rewards for unlocking achievements
  - Locked/unlocked states with visual feedback
- **Quest System**: Dynamic objective-based gameplay
  - Automatically generated quests that scale with player level
  - 9 quest types: Craft, Sell, Gold, Rarity, Materials, Reputation, Upgrades, Rivals, Weapon-specific
  - Progress tracking with visual progress bars
  - Gold and XP rewards upon completion
  - Auto-generates new quest after completion
- **Chapter System**: 5 narrative progression chapters
  - Chapter 1: The Beginning (0-500 rep)
  - Chapter 2: Building Reputation (500-2,000 rep)
  - Chapter 3: Market Competition (2,000-10,000 rep)
  - Chapter 4: Master Craftsman (10,000-50,000 rep)
  - Chapter 5: Path to Legend (50,000-100,000 rep)
  - Each chapter has specific goals and milestones
- **Leveling System**: Gain XP from crafting, earn stat points on level-up
- **4 Stats to Distribute**:
  - **Smithing**: Improves quality & reduces failure rate
  - **Efficiency**: Reduces material costs (planned feature)
  - **Speed**: Faster crafting (20% with Apprentice upgrade)
  - **Business**: Better prices & customer relations (planned feature)
- **Rank System**: Dynamic titles based on reputation
  - Novice → Apprentice → Renowned → Skilled → Expert → Master → Legendary → Blacksmith of Legend
- **Hidden Luck System**: Starts at 0, affects all RNG but never displayed to player
- **Gear System**: 7 equipment slots (Head, Arms, Body, Legs, Boots, Hammer, Accessory)
  - 7 perk types: Luck, Smithing, Efficiency %, Speed %, Business %, Gold Find %, XP Bonus %
  - 23 unique gear perks with varying bonuses
  - Currently only Luck perks are fully functional

### Dynamic World
- **Randomized Rival Blacksmiths**: 2-4 competitors per playthrough
  - 5 Archetypes: Bulk Producer, Luxury Craftsman, Speed Specialist, Generalist, Specialist
  - Procedurally generated names
  - Track market share and watch rivals close down as you dominate
- **World Events**: War, Peace, Festivals, Harsh Winters, etc.
  - Affect material costs, weapon demand, and customer budgets
  - Season-aware events (Harsh Winter only in winter, etc.)
  - Last 60 seconds each
  - Appear every 5-10 minutes for impactful pacing
- **Choice Events**: Moral dilemmas with hidden consequences
  - Choices secretly affect hidden luck stat
  - No indication of "correct" answers
  - Examples: Mysterious Beggar, Broken Heirloom, Traveling Merchant

### Economy & Services
- **Dynamic Pricing**: Market conditions affect costs and sale prices
- **Customer System**: NPCs with budgets and quality requirements
- **Bank Loans**: Borrow gold at 15% interest (no game over on bankruptcy)
- **Contracts**: Client-provided materials for guaranteed low-paying work
- **Spiritual Services**: Temple prayers and forge offerings (recovery mechanics for negative luck)

### Information & Strategy
- **Town Notice Board**: Critical information about world events, rivals, and market trends
  - No notifications - players must actively check
  - Hints at upcoming events without revealing mechanics
- **Market Intelligence**: Track rival performance and market share
- **Activity Log**: Detailed history of all actions and events
- **Achievement Tracking**: Visual progress toward 40+ achievements
- **Active Quest Display**: Current objective with progress bar in status panel

## 🎯 Victory Condition

Reach **100,000 Reputation** to become the Legendary Master Smith and achieve the rank of **Blacksmith of Legend**!

## 💾 Save System

- **2 Save Slots**: Independent saves with detailed information
- **Auto-Save**: Automatically saves to Slot 1 every 2 minutes
- **Manual Save/Load**: Access via floating button (top-right)
- **Save Data Includes**: Forge name, level, gold, reputation, achievements, quest progress, timestamp, and full game state
- **Last Saved Indicator**: Shows time since last save below Save/Load button

## 🎲 Design Philosophy

### Replayability Through Mystery
- **Hidden Luck**: Never revealed to players, creates genuine surprise
- **No Tooltips**: Players learn through experimentation
- **Discovery-Based**: Important information requires active seeking (notice board)
- **Procedural Generation**: Different rivals, events, and outcomes each playthrough
- **Random Start Dates**: Each game begins in a random month for variety

### Risk vs. Reward
- **Harsh Failures**: Lost materials create meaningful decisions
- **No Game Over**: Always a path to recovery through contracts or loans
- **Strategic Choices**: Balance quality vs. safety, investment vs. stability

### Skill Differentiation
- Attentive players who check the notice board gain competitive advantages
- Understanding hidden mechanics (like luck recovery) improves performance
- Market awareness and timing decisions matter
- Quest completion rewards consistent progression

### Guided Progression
- **Quests**: Always have a clear short-term objective
- **Achievements**: Long-term goals and milestones to work toward
- **Chapters**: Narrative structure guiding reputation progression

## 🛠️ Technical Details

- **Platform**: Browser-based (HTML/CSS/JavaScript)
- **Storage**: LocalStorage (browser-local saves)
- **No Dependencies**: Pure vanilla JavaScript
- **File Size**: Single ~100KB HTML file
- **Compatibility**: Modern browsers (Chrome, Firefox, Safari, Edge)
- **Version**: 1.2 (Achievements + Quests Update)

## 🚀 How to Play

1. Download `forge_master_complete.html`
2. Open in any modern web browser
3. Enter your character name and forge name
4. Start crafting and selling!

**OR**

Visit the [GitHub Pages deployment](#) *(coming soon)*

## 📋 Current Version: 1.2 (December 2024)

### Latest Features ✨
✅ **Achievement System** - 40+ achievements across 8 categories with rewards  
✅ **Quest System** - Dynamic objectives that scale with level (9 quest types)  
✅ **Chapter Progression** - 5 narrative chapters guiding your journey  
✅ **Rank Titles** - Dynamic titles based on reputation  
✅ **Enhanced Gear** - 7 perk types (Luck, Smithing, Efficiency, Speed, Business, Gold Find, XP)  
✅ **Calendar System** - Fantasy seasons with standard months  
✅ **Quest Progress Tracking** - Visual progress bars for active quests  

### Core Features
✅ Full crafting system with rarities and perks  
✅ Leveling and stat distribution  
✅ Hidden luck system with gear bonuses  
✅ Rival blacksmith competition  
✅ World events and choice events  
✅ Notice board and market intelligence  
✅ Save/load system (2 slots with auto-save)  
✅ Bank loans and contracts  
✅ No game-over recovery systems  

### Planned Features (Phase 1-4)
⏳ **Phase 1**: XP/Reputation progress bars, Upgrade unlock previews, Phased feature unlocking  
⏳ **Phase 2**: Efficiency/Speed/Business stat implementation, Gear stat bonuses (non-luck), Batch crafting  
⏳ **Phase 3**: Special order system, Material expeditions, Daily login bonuses, Smithing competitions  
⏳ **Phase 4**: Tutorial system, Sound effects, Offline progress, Prestige/New Game+  

See [FORGE_MASTER_TODO.md](FORGE_MASTER_TODO.md) for detailed roadmap.

## 🐛 Known Issues

- Some gear stat bonuses not yet implemented (Efficiency %, Speed %, Business %, Gold Find %, XP Bonus %)
- Debt collateral system tracked but not actively used

## 🤝 Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for:
- Bug fixes
- Balance adjustments
- New events or content
- UI/UX improvements
- Additional features

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Credits

Created with Claude AI assistance

Inspired by classic blacksmith simulation games and incremental/idle game design.

## 🎮 Tips for New Players

1. **Complete quests for steady rewards** - they provide gold and XP to keep you progressing
2. **Check achievements tab** - see what milestones you're working toward
3. **Check the Notice Board regularly** - world events can make or break your profits
4. **Don't ignore your rivals** - monitor the Market tab to see your competition
5. **Balance risk and reward** - expensive materials can fail, start with iron
6. **Distribute stats wisely** - Smithing reduces failures and improves quality
7. **Customers are picky** - match their weapon type and quality requirements
8. **Use contracts when broke** - guaranteed income when you need it
9. **Craft gear for luck bonuses** - costs 100g but can improve all your results
10. **Follow chapter goals** - they guide you through the game's progression
11. **Temple prayers aren't just flavor** - pay attention to patterns (wink)
12. **Save often** - use both save slots for different strategies

## 📞 Support

Found a bug? Have a suggestion? Open an issue on GitHub!

---

**May your hammer strike true and your forge burn bright!** ⚒️🔥