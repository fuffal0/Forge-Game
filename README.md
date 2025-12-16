# ⚒️ Forge Master - Blacksmith Tycoon

A text-based blacksmith simulation game where you start with a humble forge and work your way to becoming the Legendary Master Smith of the realm.

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
- **Leveling System**: Gain XP from crafting, earn stat points on level-up
- **4 Stats to Distribute**:
  - **Smithing**: Improves quality & reduces failure rate
  - **Efficiency**: Reduces material costs (future feature)
  - **Speed**: Faster crafting
  - **Business**: Better prices & customer relations
- **Hidden Luck System**: Starts at 0, affects all RNG but never displayed to player
- **Gear System**: 7 equipment slots (Head, Arms, Body, Legs, Boots, Hammer, Accessory)
  - Each gear piece provides +1 to +10 Luck bonus
  - Higher hidden luck = better chance at high gear rolls

### Dynamic World
- **Randomized Rival Blacksmiths**: 2-4 competitors per playthrough
  - 5 Archetypes: Bulk Producer, Luxury Craftsman, Speed Specialist, Generalist, Specialist
  - Procedurally generated names
  - Track market share and watch rivals close down as you dominate
- **World Events**: War, Peace, Festivals, Harsh Winters, etc.
  - Affect material costs, weapon demand, and customer budgets
  - Last 60 seconds each
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

## 🎯 Victory Condition

Reach **100,000 Reputation** to become the Legendary Master Smith!

## 💾 Save System

- **2 Save Slots**: Independent saves with detailed information
- **Auto-Save**: Automatically saves to Slot 1 every 30 seconds
- **Manual Save/Load**: Access via floating button (top-right)
- **Save Data Includes**: Forge name, level, gold, reputation, timestamp, and full game state

## 🎲 Design Philosophy

### Replayability Through Mystery
- **Hidden Luck**: Never revealed to players, creates genuine surprise
- **No Tutorials**: Players learn through experimentation
- **Discovery-Based**: Important information requires active seeking (notice board)
- **Procedural Generation**: Different rivals, events, and outcomes each playthrough

### Risk vs. Reward
- **Harsh Failures**: Lost materials create meaningful decisions
- **No Game Over**: Always a path to recovery through contracts or loans
- **Strategic Choices**: Balance quality vs. safety, investment vs. stability

### Skill Differentiation
- Attentive players who check the notice board gain competitive advantages
- Understanding hidden mechanics (like luck recovery) improves performance
- Market awareness and timing decisions matter

## 🛠️ Technical Details

- **Platform**: Browser-based (HTML/CSS/JavaScript)
- **Storage**: LocalStorage (browser-local saves)
- **No Dependencies**: Pure vanilla JavaScript
- **File Size**: Single ~75KB HTML file
- **Compatibility**: Modern browsers (Chrome, Firefox, Safari, Edge)

## 🚀 How to Play

1. Download `forge_master.html`
2. Open in any modern web browser
3. Enter your character name and forge name
4. Start crafting and selling!

**OR**

Visit the [GitHub Pages deployment](#) *(coming soon)*

## 📋 Current Version: 1.0

### Known Features
✅ Full crafting system with rarities and perks  
✅ Leveling and stat distribution  
✅ Hidden luck system with gear bonuses  
✅ Rival blacksmith competition  
✅ World events and choice events  
✅ Notice board and market intelligence  
✅ Save/load system (2 slots)  
✅ Bank loans and contracts  
✅ No game-over recovery systems  

### Planned Features
⏳ Efficiency stat implementation  
⏳ More world events and choice scenarios  
⏳ Achievement system  
⏳ New Game+ mode  
⏳ Additional weapon and armor types  
⏳ Guild system  
⏳ Regional expansion mechanics  

## 🐛 Known Issues

*None reported yet - please open an issue if you find bugs!*

## 🤝 Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for:
- Bug fixes
- Balance adjustments
- New events or content
- UI/UX improvements
- Additional features

## 📜 License

This project is licensed under the MIT License - see the License file for details.

## 👨‍💻 Credits

Created by [Your Name]

Inspired by classic blacksmith simulation games and incremental/idle game design.

## 🎮 Tips for New Players

1. **Check the Notice Board regularly** - world events can make or break your profits
2. **Don't ignore your rivals** - monitor the Market tab to see your competition
3. **Balance risk and reward** - expensive materials can fail, start with iron
4. **Distribute stats wisely** - Smithing reduces failures, invest early
5. **Customers are picky** - match their weapon type and quality requirements
6. **Use contracts when broke** - guaranteed income when you need it
7. **Temple prayers aren't just flavor** - pay attention to patterns (wink)
8. **Save often** - use both save slots for different strategies

## 📞 Support

Found a bug? Have a suggestion? Open an issue on GitHub!

---

**May your hammer strike true and your forge burn bright!** ⚒️🔥