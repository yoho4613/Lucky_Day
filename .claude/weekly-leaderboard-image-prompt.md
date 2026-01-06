# Weekly Leaderboard Image Generation Prompts

## For AI Image Generators (Midjourney, DALL-E, etc.)

### Main Banner (1200x630px - Landscape)

```
Create a modern gaming promotional banner for "Weekly Leaderboard".

Design specs:
- Dark gradient background (deep purple #1a1a2e to navy #16213e)
- Large golden trophy icon in the center top
- Title: "WEEKLY LEADERBOARD" in bold white/gold text
- Reward table showing:
  🥇 3 TON + 10,000 CLUBS
  🥈 1 TON + 5,000 CLUBS
  🥉 0.5 TON + 2,500 CLUBS
- Three category icons at bottom: slot machine (Spins), diamond (Clubs), people group (Referrals)
- Subtle glow effects and particle sparkles
- Gaming/crypto aesthetic
- Text: "Resets Every Monday"
- Dimensions: 1200x630px landscape
- Style: Modern, sleek, professional gaming banner
```

### Square Banner (1080x1080px - Social Media)

```
Create a square social media banner for crypto gaming rewards.

Design specs:
- Dark purple/blue gradient background
- Golden trophy at top center
- Title: "WEEKLY REWARDS"
- Reward list:
  🥇 3 TON + 10K CLUBS
  🥈 1 TON + 5K CLUBS
  🥉 0.5 TON + 2.5K CLUBS
- Text: "TOP 5 GET REWARDED!"
- Three icons: 🎰 SPINS | 💎 CLUBS | 👥 REFERRALS
- Neon glow effects
- Dimensions: 1080x1080px square
- Style: Crypto/Web3 gaming aesthetic
```

### Story Banner (1080x1920px - Vertical)

```
Create a vertical story-format banner for mobile gaming promotion.

Design specs:
- Full dark gradient background
- Large trophy icon at top
- "WEEKLY LEADERBOARD" title
- Vertical reward list:
  🥇 3 TON + 10k CLUBS
  🥈 1 TON + 5k CLUBS
  🥉 0.5 TON + 2500 CLUBS
  4th 0.2 TON + 1000 CLUBS
  5th 0.2 TON + 500 CLUBS
- "+ BONUS CLUBS" text
- "3 CATEGORIES" section with Spins, Clubs, Referrals
- "PLAY NOW!" call to action at bottom
- Dimensions: 1080x1920px vertical
- Style: Mobile-first, gaming app promotion
```

---

## SVG Banner Code (Ready to Use)

### Main Banner SVG

```svg
<svg width="1200" height="630" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="bgGrad" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#1a1a2e"/>
      <stop offset="100%" style="stop-color:#16213e"/>
    </linearGradient>
    <linearGradient id="goldGrad" x1="0%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%" style="stop-color:#FFD700"/>
      <stop offset="100%" style="stop-color:#FFA500"/>
    </linearGradient>
    <filter id="glow">
      <feGaussianBlur stdDeviation="3" result="coloredBlur"/>
      <feMerge>
        <feMergeNode in="coloredBlur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>
  </defs>

  <!-- Background -->
  <rect width="1200" height="630" fill="url(#bgGrad)"/>

  <!-- Trophy Icon -->
  <text x="600" y="100" text-anchor="middle" font-size="72" filter="url(#glow)">🏆</text>

  <!-- Title -->
  <text x="600" y="170" text-anchor="middle" font-family="Arial Black, sans-serif" font-size="48" fill="url(#goldGrad)" font-weight="bold">WEEKLY LEADERBOARD</text>

  <!-- Subtitle -->
  <text x="600" y="210" text-anchor="middle" font-family="Arial, sans-serif" font-size="20" fill="#FFFFFF" opacity="0.8">Compete for REAL TON Rewards Every Week!</text>

  <!-- Rewards Box -->
  <rect x="350" y="240" width="500" height="240" rx="16" fill="#FFFFFF" opacity="0.1"/>

  <!-- Reward Lines -->
  <text x="420" y="290" font-family="Arial, sans-serif" font-size="28" fill="#FFD700">🥇</text>
  <text x="470" y="290" font-family="Arial, sans-serif" font-size="24" fill="#FFFFFF" font-weight="bold">3 TON + 10,000 CLUBS</text>

  <text x="420" y="335" font-family="Arial, sans-serif" font-size="28" fill="#C0C0C0">🥈</text>
  <text x="470" y="335" font-family="Arial, sans-serif" font-size="24" fill="#FFFFFF" font-weight="bold">1 TON + 5,000 CLUBS</text>

  <text x="420" y="380" font-family="Arial, sans-serif" font-size="28" fill="#CD7F32">🥉</text>
  <text x="470" y="380" font-family="Arial, sans-serif" font-size="24" fill="#FFFFFF" font-weight="bold">0.5 TON + 2,500 CLUBS</text>

  <text x="420" y="425" font-family="Arial, sans-serif" font-size="22" fill="#AAAAAA">4th</text>
  <text x="470" y="425" font-family="Arial, sans-serif" font-size="20" fill="#CCCCCC">0.2 TON + 1,000 CLUBS</text>

  <text x="420" y="465" font-family="Arial, sans-serif" font-size="22" fill="#AAAAAA">5th</text>
  <text x="470" y="465" font-family="Arial, sans-serif" font-size="20" fill="#CCCCCC">0.2 TON + 500 CLUBS</text>

  <!-- Categories -->
  <text x="300" y="550" text-anchor="middle" font-size="36">🎰</text>
  <text x="300" y="585" text-anchor="middle" font-family="Arial, sans-serif" font-size="16" fill="#FFFFFF">SPINS</text>

  <text x="600" y="550" text-anchor="middle" font-size="36">💎</text>
  <text x="600" y="585" text-anchor="middle" font-family="Arial, sans-serif" font-size="16" fill="#FFFFFF">CLUBS</text>

  <text x="900" y="550" text-anchor="middle" font-size="36">👥</text>
  <text x="900" y="585" text-anchor="middle" font-family="Arial, sans-serif" font-size="16" fill="#FFFFFF">REFERRALS</text>

  <!-- Timer badge -->
  <rect x="480" y="500" width="240" height="32" rx="16" fill="#8B5CF6"/>
  <text x="600" y="522" text-anchor="middle" font-family="Arial, sans-serif" font-size="14" fill="#FFFFFF">⏰ Resets Every Monday</text>
</svg>
```

### Square Banner SVG (1080x1080)

```svg
<svg width="1080" height="1080" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="bgGrad2" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#1a1a2e"/>
      <stop offset="100%" style="stop-color:#16213e"/>
    </linearGradient>
    <linearGradient id="goldGrad2" x1="0%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%" style="stop-color:#FFD700"/>
      <stop offset="100%" style="stop-color:#FFA500"/>
    </linearGradient>
  </defs>

  <!-- Background -->
  <rect width="1080" height="1080" fill="url(#bgGrad2)"/>

  <!-- Trophy -->
  <text x="540" y="150" text-anchor="middle" font-size="100">🏆</text>

  <!-- Title -->
  <text x="540" y="250" text-anchor="middle" font-family="Arial Black, sans-serif" font-size="56" fill="url(#goldGrad2)" font-weight="bold">WEEKLY REWARDS</text>

  <!-- Rewards Box -->
  <rect x="140" y="300" width="800" height="420" rx="20" fill="#FFFFFF" opacity="0.1"/>

  <!-- Rewards -->
  <text x="200" y="380" font-size="48">🥇</text>
  <text x="280" y="380" font-family="Arial, sans-serif" font-size="36" fill="#FFFFFF" font-weight="bold">3 TON + 10,000 CLUBS</text>

  <text x="200" y="460" font-size="48">🥈</text>
  <text x="280" y="460" font-family="Arial, sans-serif" font-size="36" fill="#FFFFFF" font-weight="bold">1 TON + 5,000 CLUBS</text>

  <text x="200" y="540" font-size="48">🥉</text>
  <text x="280" y="540" font-family="Arial, sans-serif" font-size="36" fill="#FFFFFF" font-weight="bold">0.5 TON + 2,500 CLUBS</text>

  <text x="200" y="620" font-family="Arial, sans-serif" font-size="32" fill="#AAAAAA">4th</text>
  <text x="280" y="620" font-family="Arial, sans-serif" font-size="28" fill="#CCCCCC">0.2 TON + 1,000 CLUBS</text>

  <text x="200" y="690" font-family="Arial, sans-serif" font-size="32" fill="#AAAAAA">5th</text>
  <text x="280" y="690" font-family="Arial, sans-serif" font-size="28" fill="#CCCCCC">0.2 TON + 500 CLUBS</text>

  <!-- Top 5 Badge -->
  <rect x="340" y="760" width="400" height="50" rx="25" fill="#8B5CF6"/>
  <text x="540" y="795" text-anchor="middle" font-family="Arial, sans-serif" font-size="24" fill="#FFFFFF" font-weight="bold">TOP 5 GET REWARDED!</text>

  <!-- Categories -->
  <text x="240" y="900" text-anchor="middle" font-size="60">🎰</text>
  <text x="240" y="960" text-anchor="middle" font-family="Arial, sans-serif" font-size="24" fill="#FFFFFF">SPINS</text>

  <text x="540" y="900" text-anchor="middle" font-size="60">💎</text>
  <text x="540" y="960" text-anchor="middle" font-family="Arial, sans-serif" font-size="24" fill="#FFFFFF">CLUBS</text>

  <text x="840" y="900" text-anchor="middle" font-size="60">👥</text>
  <text x="840" y="960" text-anchor="middle" font-family="Arial, sans-serif" font-size="24" fill="#FFFFFF">REFERRALS</text>

  <!-- Timer -->
  <text x="540" y="1040" text-anchor="middle" font-family="Arial, sans-serif" font-size="20" fill="#FFFFFF" opacity="0.7">⏰ Resets Every Monday 00:00 UTC</text>
</svg>
```

---

## Canva/Figma Design Specs

**Colors:**

- Background Dark: #1a1a2e
- Background Light: #16213e
- Gold: #FFD700
- Gold Dark: #FFA500
- Purple Accent: #8B5CF6
- White: #FFFFFF
- Gray: #AAAAAA, #CCCCCC

**Fonts:**

- Title: Arial Black, Poppins Bold, or Inter Bold
- Body: Arial, Poppins, or Inter
- Sizes: Title 48-56px, Rewards 24-36px, Categories 16-24px

**Effects:**

- Subtle glow on trophy and title
- Rounded corners (16-20px) on boxes
- Semi-transparent white overlays (10-15% opacity)
