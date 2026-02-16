# 🏈 AFL Training: The Arise System

**Raoul's Elite AFL Programme** - Level up your footy skills with daily quests!

Inspired by Solo Leveling, this PWA gamifies AFL training with Sung Jin-Woo as your training system guide.

## 👑 Theme Features

- **Main Menu**: Sung Jin-Woo Shadow Monarch background
- **Endurance Quest**: Sung Jin-Woo "ARISE" moment
- **Other Quests**: Character-themed backgrounds (Killua, Luffy, AFL players)

## ⚡ Features

### 6 Quest Types
- ⚡ God Speed (Sprint - Killua theme)
- 🎯 Drop Punt Master (Kicking - Errol Gulden)
- 👊 Bullet Handballs (Handball - Monkey D. Luffy)
- 🦅 Sky High Marks (Marking - Charlie Curnow) *Unlockable*
- ⚽ Danger Field (Ground Balls - Isaac Heeney) *Unlockable*
- 🏃 Endless Stamina (Endurance - Jin-Woo ARISE) *Unlockable*

### Game System
- Level up from E-RANK to S-RANK
- Track AGI, STA, STR stats
- Earn XP from completing quests
- Unlock advanced quests after completing 3

### PWA Features
- Install on phone
- Works offline
- Auto-saves progress
- Responsive design

## 🚀 Quick Start

### Use GitHub Pages
1. Go to Settings → Pages
2. Enable Pages (main branch)
3. Visit: `https://alexalfarosoto-source.github.io/raouls-elite-AFL-programme`
4. On phone: "Add to Home Screen"

### Run Locally
1. Clone repo: `git clone https://github.com/alexalfarosoto-source/raouls-elite-AFL-programme.git`
2. Open `index.html` in browser

## 📱 Install on Mobile

**iPhone**: Safari → Share → Add to Home Screen

**Android**: Chrome → Menu → Install app

## 🎮 Usage

1. Choose a quest from the main menu
2. Select difficulty level
3. Complete the training
4. Earn XP and stat increases
5. Level up and unlock new quests!

## 🖼️ Custom Backgrounds

Want your own Sung Jin-Woo images?

1. Upload images to Imgur
2. Get direct image URLs
3. Edit `index.html`:
   - Find `QUEST_BACKGROUNDS` (line ~300)
   - Find `backgroundImage:` in QuestSelectScreen (line ~800)
   - Replace URLs

## 📊 Quest Details

| Quest | Type | Rewards | Unlock |
|-------|------|---------|--------|
| Speed | Timed (3x) | +2 AGI, +150 XP | Start |
| Kicking | Dual Counter | +2 STR, +1 AGI, +150 XP | Start |
| Handball | Dual Counter | +2 AGI, +1 STA, +150 XP | Start |
| Marks | Counter | +2 STR, +2 AGI, +200 XP | After 3 |
| Ground Balls | Dual Counter | +2 AGI, +1 STA, +180 XP | After 3 |
| Endurance | Timed | +3 STA, +1 AGI, +200 XP | After 3 |

## 🔧 Tech Stack

- React 18 (CDN)
- Tailwind CSS
- LocalStorage
- Service Worker
- PWA APIs

## 📄 License

MIT

---

**"ARISE" and become an S-RANK AFL athlete! 👑⚡🏈**