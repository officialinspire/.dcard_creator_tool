# 🃏 DCARD Format v2.0 - Digital Collectibles System

**Premium card packaging for INSPIRE Network digital collectibles and rewards**

Distribute unique, verifiable digital collectibles across your network of websites:
- 🌿 **iSmokeShop.net** - Cannabis culture collectibles
- 🎨 **InspireClothing.art** - Creative art collectibles  
- 🎮 **DantesWorld.art** - Game achievement rewards

---

## ⚡ What's New in v2.0

### 🎁 Collectible & Rewards System
- **Reward Cards**: Mark cards as achievement rewards with unlock conditions
- **Limited Editions**: Mint numbers and serial tracking (#0001/1000)
- **Network Attribution**: Tag cards by INSPIRE network brand

### 💎 Specialty Badges & Overlays
- **10 Badge Presets**: Diamond, Gold, Skull, Fire, Leaf, Star, Crystal, Crown, Lightning, Heart
- **Custom Positions**: Top-left, top-right, bottom-left, bottom-right
- **Numbered Badges**: Add numbers and custom colors to badges
- **Specialty Overlays**: Diamond patterns, skull overlays, custom effects

### ✨ Enhanced Visual Effects
- **Glow Effects**: Customizable color and intensity
- **Particle Systems**: Sparkles, stars, embers, snow
- **Advanced Borders**: Solid, gradient, and animated styles
- **Shadow Control**: Custom color and blur settings

### 🎨 Neumorphism UI
- Modern soft-shadow design aesthetic
- Smooth animations and transitions
- Responsive layout for all devices
- Tabbed interface for better organization

---

## 🚀 Quick Start

### 1. Open the Creator Tool

Simply open `dcard-creator-v2.html` in your browser. No installation required!

### 2. Create Your First Card

**Metadata Tab:**
- Enter card name (e.g., "Cosmic Fire Dragon")
- Select brand (INSPIRE, iSmokeShop, DANTES WORLD)
- Set rarity (Common → Mythic)
- Add description and flavor text

**Assets Tab:**
- Upload front image (required)
- Upload back image (optional)
- Add holographic pattern
- Upload brand/set logos
- Add theme music

**Badges & Effects Tab:**
- Click badge icons to add them
- Toggle visual effects (glow, particles, borders)
- Customize holographic settings
- Adjust effect colors and intensities

**Collectible Tab:**
- Mark as reward card (optional)
- Set unlock conditions
- Configure mint numbers for limited editions

**Advanced Tab:**
- Fine-tune animations
- Adjust lighting settings
- Set creator information

### 3. Generate & Download

Click **🚀 Create DCARD** to generate your `.dcard` file. The file downloads automatically!

---

## 📦 File Structure v2.0

```json
{
  "format": "dcard",
  "version": "2.0",
  "fingerprint": "SHA256_hash",
  
  "metadata": {
    "cardId": "unique-id",
    "name": "Card Name",
    "caption": "Subtitle text",
    "brand": "INSPIRE",
    "set": "Alpha Collection",
    "cardNumber": "001",
    "totalInSet": "100",
    "rarity": "legendary",
    "category": "character",
    
    "collectible": {
      "isReward": true,
      "rewardFor": "Complete Level 10",
      "unlockCondition": "Reach 1000 points",
      "mintNumber": 42,
      "totalMinted": 1000,
      "serialNumber": "#0042/1000"
    }
  },
  
  "assets": {
    "cardFront": {...},
    "cardBack": {...},
    "holographicPattern": {...},
    "specialtyOverlay": {...},
    "brandLogo": {...},
    "setLogo": {...},
    "audio": {...}
  },
  
  "display": {
    "holographic": {
      "enabled": true,
      "intensity": 0.7,
      "pattern": "rainbow",
      "speed": 1.0
    },
    
    "badges": [
      {
        "type": "diamond",
        "position": "top-right",
        "number": 1,
        "color": "#00d4ff",
        "animation": "pulse"
      }
    ],
    
    "effects": {
      "glow": true,
      "glowColor": "#00ff88",
      "glowIntensity": 0.5,
      
      "particles": true,
      "particleType": "sparkles",
      "particleCount": 20,
      
      "border": true,
      "borderStyle": "gradient",
      
      "shadow": true
    }
  }
}
```

---

## 💎 Specialty Badges

### Available Badge Presets

| Badge | Icon | Best For |
|-------|------|----------|
| **Diamond** | 💎 | Premium/VIP cards |
| **Gold** | 🥇 | First place rewards |
| **Skull** | 💀 | Dark/gothic themes |
| **Fire** | 🔥 | Power/energy cards |
| **Leaf** | 🍃 | Nature/cannabis themes |
| **Star** | ⭐ | Achievement stars |
| **Crystal** | 💠 | Rare collectibles |
| **Crown** | 👑 | Royalty/leadership |
| **Lightning** | ⚡ | Speed/power |
| **Heart** | ❤️ | Favorite/loved items |

### Adding Badges Programmatically

```javascript
const card = await dcard.create({...});

// Add diamond badge to top-right
dcard.addBadge(card, {
    type: 'diamond',
    position: 'top-right',
    number: 1,
    color: '#00d4ff',
    size: 'large',
    animation: 'pulse'
});

// Add multiple badges
dcard.addBadge(card, { type: 'star', position: 'top-left' });
dcard.addBadge(card, { type: 'fire', position: 'bottom-right' });
```

---

## 🎁 Reward System Integration

### Creating Reward Cards

```javascript
const rewardCard = await dcard.create({
    name: 'Master Cultivator',
    brand: 'iSmokeShop',
    rarity: 'legendary',
    isReward: true,
    rewardFor: 'Complete Cultivation Course',
    unlockCondition: 'Finish all 10 lessons',
    cardFront: await dcard.imageToAsset(imageFile)
});

// Automatically adds a star badge
dcard.setAsReward(rewardCard, {
    rewardFor: 'Level 10 Achievement',
    unlockCondition: 'Complete expert challenges',
    addBadge: true  // Adds star badge
});
```

### Limited Edition Cards

```javascript
// Create limited edition card
const limitedCard = await dcard.create({
    name: 'Founder\'s Edition',
    brand: 'INSPIRE',
    mintNumber: 42,
    totalMinted: 100,
    cardFront: frontAsset
});

// Or set later
dcard.setMintInfo(limitedCard, 42, 100);
// Results in serial: #0042/0100
```

---

## ✨ Visual Effects Guide

### Glow Effects

```javascript
{
    glowEffect: true,
    glowColor: '#00ff88',
    glowIntensity: 0.7
}
```

Perfect for: Mystical cards, power-ups, rare collectibles

### Particle Effects

```javascript
{
    particleEffect: true,
    particleType: 'sparkles',  // or 'stars', 'embers', 'snow'
    particleColor: '#ffffff',
    particleCount: 30
}
```

**Particle Types:**
- `sparkles`: Magic/enchantment
- `stars`: Achievement/celebration
- `embers`: Fire/heat themes
- `snow`: Ice/winter themes

### Border Styles

```javascript
{
    borderEffect: true,
    borderStyle: 'gradient',  // or 'solid', 'animated'
    borderColor: '#00ff88',
    borderWidth: 3
}
```

### Shadow Depth

```javascript
{
    shadowEffect: true,
    shadowColor: '#000000',
    shadowBlur: 25
}
```

---

## 🎮 Use Cases

### 1. Game Achievement Rewards

```javascript
// Create reward for completing a game level
const achievementCard = await dcard.create({
    name: 'Level 10 Master',
    brand: 'DANTES WORLD',
    category: 'achievement',
    isReward: true,
    rewardFor: 'Complete Level 10',
    unlockCondition: 'Beat final boss',
    badges: [
        { type: 'crown', position: 'top-right' },
        { type: 'star', position: 'top-left', number: 10 }
    ],
    glowEffect: true,
    glowColor: '#ffd700'
});
```

### 2. Limited Edition Cannabis Strain Cards

```javascript
// Limited edition strain collectible
const strainCard = await dcard.create({
    name: 'OG Kush - Founder\'s Cut',
    brand: 'iSmokeShop',
    category: 'strain',
    rarity: 'legendary',
    mintNumber: 1,
    totalMinted: 420,
    badges: [
        { type: 'leaf', position: 'top-right', color: '#00ff88' },
        { type: 'diamond', position: 'top-left' }
    ],
    particleEffect: true,
    particleType: 'sparkles'
});
```

### 3. Art Collectibles

```javascript
// Limited art piece
const artCard = await dcard.create({
    name: 'Cosmic Dreams #7',
    brand: 'INSPIRE',
    artist: 'Jane Doe',
    category: 'artwork',
    rarity: 'rare',
    mintNumber: 7,
    totalMinted: 25,
    holographicIntensity: 0.9,
    badges: [
        { type: 'crystal', position: 'top-right', number: 7 }
    ]
});
```

### 4. Customer Loyalty Rewards

```javascript
// VIP member card
const vipCard = await dcard.create({
    name: 'Diamond Member',
    brand: 'iSmokeShop',
    category: 'membership',
    rarity: 'legendary',
    badges: [
        { type: 'diamond', position: 'top-right', size: 'large' },
        { type: 'crown', position: 'top-left' }
    ],
    glowEffect: true,
    glowColor: '#00d4ff',
    borderStyle: 'gradient'
});
```

---

## 🌐 Network Distribution

### Integration Across INSPIRE Network

```javascript
// iSmokeShop.net - Cannabis collectibles
const smokeCard = await dcard.create({
    brand: 'iSmokeShop',
    network: 'INSPIRE',
    category: 'strain'
});

// InspireClothing.art - Art collectibles
const artCard = await dcard.create({
    brand: 'INSPIRE',
    network: 'INSPIRE',
    category: 'artwork'
});

// DantesWorld.art - Game rewards
const gameCard = await dcard.create({
    brand: 'DANTES WORLD',
    network: 'INSPIRE',
    category: 'achievement',
    isReward: true
});
```

### Sharing Cards

All `.dcard` files include:
- `shareable`: true/false flag
- `shareMessage`: Custom share text
- `network`: INSPIRE network attribution

```javascript
card.interactive.shareable = true;
card.interactive.shareMessage = "Check out my rare collectible from iSmokeShop!";
```

---

## 🔒 Verification & Authenticity

### Fingerprinting

Each card has a unique SHA-256 fingerprint:

```javascript
console.log(card.fingerprint);
// "a3f5d8e2b1c4a9f7e6d5c3b2a1f0e9d8..."
```

Use for:
- Detecting duplicates
- Tracking card versions
- Verifying authenticity
- Database indexing

### Checksums

```javascript
const isValid = await dcard.verify(card);
if (isValid) {
    console.log('Card is authentic!');
} else {
    console.warn('Card may be corrupted or tampered!');
}
```

### Serial Numbers

Limited editions include serial numbers:

```javascript
card.metadata.collectible.serialNumber;
// "#0042/1000"
```

---

## 📱 Mobile Optimization

The neumorphism creator is fully responsive:

✅ Touch-friendly controls  
✅ Mobile file uploads  
✅ Responsive grid layouts  
✅ Optimized for iOS Safari & Android Chrome  
✅ Smooth animations on mobile devices  

---

## 🎨 Customization Examples

### Cannabis-Themed Card

```javascript
const cannabisCard = await dcard.create({
    name: 'Purple Haze',
    brand: 'iSmokeShop',
    rarity: 'rare',
    badges: [
        { type: 'leaf', position: 'top-right', color: '#9b59b6' }
    ],
    glowEffect: true,
    glowColor: '#9b59b6',
    particleEffect: true,
    particleType: 'sparkles',
    particleColor: '#9b59b6',
    holographicPattern: 'cosmos'
});
```

### Fire/Power Theme

```javascript
const fireCard = await dcard.create({
    name: 'Inferno Dragon',
    badges: [
        { type: 'fire', position: 'top-right' },
        { type: 'skull', position: 'bottom-right' }
    ],
    glowEffect: true,
    glowColor: '#ff6600',
    particleEffect: true,
    particleType: 'embers',
    borderStyle: 'animated',
    borderColor: '#ff3300'
});
```

### Mystical/Cosmic Theme

```javascript
const cosmicCard = await dcard.create({
    name: 'Celestial Oracle',
    badges: [
        { type: 'crystal', position: 'top-right' },
        { type: 'star', position: 'top-left' }
    ],
    holographicPattern: 'cosmos',
    holographicIntensity: 0.9,
    particleEffect: true,
    particleType: 'stars',
    glowEffect: true,
    glowColor: '#00ccff'
});
```

---

## 📊 Best Practices

### File Size Management

- **Images**: Optimize to 1024x1024 or smaller
- **Audio**: Keep theme music under 30 seconds
- **Total Size**: Aim for under 5MB per card
- **Use JPEG** for photos, **PNG** for graphics

### Badge Usage

- **Don't Overdo It**: 1-3 badges maximum
- **Meaningful Placement**: Use positions strategically
- **Color Coordination**: Match badge colors to card theme
- **Animation Sparingly**: Pulse animation for emphasis only

### Effect Combinations

Great combinations:
- Glow + Particles (magical feel)
- Border + Shadow (depth and presence)
- Holographic + Glow (premium luxury)

Avoid:
- Too many effects at once
- Conflicting color schemes
- Over-the-top animations

### Rarity Guidelines

- **Common**: Basic effects, no badges
- **Uncommon**: 1 badge, subtle glow
- **Rare**: 2 badges, particles
- **Epic**: Multiple effects, animated border
- **Legendary**: Full effects suite, premium holo
- **Mythic**: Everything maxed out

---

## 🛠️ API Reference

See `DCard-v2.js` for complete API documentation.

### Core Methods

```javascript
const dcard = new DCard();

// Create card
const card = await dcard.create(options);

// Add badge
dcard.addBadge(card, badgeConfig);

// Set as reward
dcard.setAsReward(card, rewardConfig);

// Set mint info
dcard.setMintInfo(card, mintNum, totalMinted);

// Add specialty overlay
dcard.addSpecialtyOverlay(card, overlayConfig);

// Download
dcard.download(card, filename);

// Load
const loadedCard = await dcard.load(file);

// Verify
const isValid = await dcard.verify(card);

// Get stats
const stats = dcard.getStats(card);
```

---

## 📚 Resources

- **Creator Tool**: `dcard-creator-v2.html`
- **Library**: `DCard-v2.js`
- **Format Spec**: `dcard-format-spec-v2.md`
- **Integration Guide**: `integration-guide-v2.js`

---

## 🤝 INSPIRE Network

**Created for:**
- 🌿 iSmokeShop.net - Cannabis culture & collectibles
- 🎨 InspireClothing.art - Creative art & designs
- 🎮 DantesWorld.art - Gaming & achievements

**Version**: 2.0  
**Format**: `.dcard` (Dantes Card)  
**License**: INSPIRE Network Exclusive  

---

**Built with neumorphism design principles**  
**Optimized for digital collectibles & rewards**  
**Ready for cross-platform distribution** ⚡
