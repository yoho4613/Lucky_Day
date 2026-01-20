# Lucky Day - Telegram Mini App Service Documentation

## Table of Contents
- [Overview](#overview)
- [Core Features](#core-features)
- [Reward System](#reward-system)
- [Mini Games](#mini-games)
- [Monetization](#monetization)
- [User Progression](#user-progression)
- [Technical Architecture](#technical-architecture)
- [Admin Dashboard](#admin-dashboard)
- [Integrations](#integrations)

---

## Overview

**Lucky Day** is a Web3-enabled gaming and reward platform built as a Telegram Mini App. Users play skill-based mini-games to earn rewards including CLUBS tokens, TON cryptocurrency, bonus spins, and exclusive NFTs.

### Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | Next.js 16, React 19, TypeScript, Tailwind CSS v4 |
| Backend | Next.js API Routes, Supabase (PostgreSQL) |
| Blockchain | TON Network, TON Connect |
| Authentication | Telegram WebApp API |
| Payments | Telegram Stars, TON Crypto |
| Languages | English, Korean, Japanese, Chinese, Russian |

---

## Core Features

### Daily Spin System

- **1 Free Spin** every 24 hours (UTC reset)
- **Bonus Spins** from purchases, memberships, referrals, and rewards
- **Random Game Selection** - Server selects a game to prevent manipulation

### Game Flow

1. User initiates spin (daily or bonus)
2. Server creates game session with randomly selected game
3. 2-second shuffle animation plays
4. User plays the selected mini-game
5. On success: Server verifies session and grants reward
6. On failure: Optional ad-watch for retry

---

## Reward System

### Reward Pool Distribution

| Reward Type | Probability | Rarity Range |
|------------|-------------|--------------|
| CLUBS Tokens | 89.94% | Common - Legendary |
| Bonus Spins | 10.00% | Common - Legendary |
| TON Crypto | 0.05% | Epic - Legendary |
| NFT Ticket | 0.01% | Legendary |


## Mini Games

### Available Games (12 Total)

| Game | ID | Icon | Description |
|------|----|------|-------------|
| Neon Pulse | timing | Target | Hit the target at the perfect moment |
| Reflex Dodge | dodge | Lightning | Dodge incoming obstacles |
| Cyber Switch | switch | Brain | Memorize and toggle switches correctly |
| Neon Slider | slider | Numbers | Slide tiles to solve the puzzle |
| One Line | oneline | Pencil | Draw the shape without lifting |
| Cross Road | crossroad | Chicken | Navigate traffic safely |
| Neon Stack | stack | Building | Stack blocks perfectly |
| Connect Lines | connectlines | Lines | Connect matching endpoints |
| Maze Escape | maze | Compass | Find the exit path |
| Neon Hue | colormatch | Palette | Match colors quickly |
| Neon Keys | pianotiles | Piano | Tap tiles in rhythm |
| Memory Flip | memoryflip | Brain | Match card pairs |

### Game Properties

Each game has configurable:
- **Difficulty range** (min/max)
- **Active status** (can be disabled)
- **Description keys** (i18n support)
- **Color theme** (gradient styling)

---

## Monetization

### Product Categories

| Category | Description |
|----------|-------------|
| **Spins** | Bonus spin bundles (1, 3, 5, 10) |
| **Deals** | Discounted bundles with SALE badges |
| **Membership** | Recurring daily benefits |
| **Starter Pack** | New user welcome offer |
| **Special** | Limited-time high-value items |

### Payment Methods

#### Telegram Stars
- Fixed pricing in Stars
- Instant processing via Telegram
- Approximate rate: 1 Star = $0.013 USD

#### TON Cryptocurrency
- Dynamic pricing based on TON/USD rate
- Requires TON Connect wallet
- 60-second blockchain confirmation
- Optional 10% discount (configurable)

### Membership System

| Duration | Benefits |
|----------|----------|
| 7 Days | Daily bonus spins + CLUBS |
| 30 Days | Daily bonus spins + CLUBS |
| 90 Days | Daily bonus spins + CLUBS |

Memberships are stackable and provide:
- Extra daily spins
- Daily CLUBS bonus
- Ad-free experience (optional)

---

## User Progression

### Leaderboards

#### All-Time Leaderboard
- Total CLUBS earned
- Total spins completed
- Total referrals

#### Weekly Leaderboard
- Resets every Monday 00:00 UTC
- Top 5 receive CLUBS + Bonus Spins
- Excludes previous weekly winners

### Referral System

#### Invitee Rewards
- 250 CLUBS on signup
- 3 Bonus Spins

#### Inviter Revenue Share
- 1% of invitee's CLUBS winnings
- 10x CLUBS on invitee's purchases (e.g., $5 purchase = 50 CLUBS)

### Task System

| Task Type | Examples |
|-----------|----------|
| Social | Join Telegram channel, Follow on Twitter |
| Integration | Connect wallet, Start bot |
| Activity | Play games, Watch ads |

Tasks reward CLUBS and bonus spins upon completion.

### Check-In System

- Daily consecutive login bonuses
- Progressive rewards for streaks
- Resets on missed days

---

## Technical Architecture

### Database Tables

| Table | Purpose |
|-------|---------|
| users | User profiles and balances |
| game_history | Game play records |
| game_sessions | Active game session validation |
| purchases | Transaction history |
| ton_winners | TON payment queue |
| referrals | Referral relationships |
| tasks | Achievement tracking |
| leaderboard_snapshot | Weekly standings |
| user_memberships | Subscription records |

### Key API Endpoints

| Endpoint | Purpose |
|----------|---------|
| `/api/app/init` | Initialize user session |
| `/api/game/start` | Create game session |
| `/api/game/complete` | Verify and complete game |
| `/api/rewards/claim` | Claim pending rewards |
| `/api/shop/create-invoice` | Create Stars payment |
| `/api/shop/ton-checkout` | Create TON transaction |
| `/api/leaderboard` | Get rankings |
| `/api/referral` | Manage referrals |

### Security Features

- **Server-side game selection** - Prevents manipulation
- **Session-based validation** - Games must complete within 5 minutes
- **Rate limiting** - 1-second minimum between game starts
- **TON transaction verification** - Blockchain confirmation
- **JWT authentication** - Admin dashboard protection

---

## Admin Dashboard

### Available Pages

| Page | Features |
|------|----------|
| **Overview** | Key metrics: users, revenue, spins, pending payouts |
| **Users** | Search, view details, grant bonus spins |
| **Spins** | Analytics by day/period, reward distribution |
| **Rewards** | Probability display, expected values |
| **Revenue** | Stars vs TON breakdown, transaction history |
| **Products** | CRUD for shop items |
| **Payouts** | Process TON winners, NFT minting |
| **Broadcast** | Send messages to all users |
| **Announcement** | Weekly leaderboard results |
| **Partners** | Partner tracking and analytics |
| **Campaigns** | Marketing campaign performance |

### Authentication

- Email/password login
- JWT tokens (24-hour expiry)
- httpOnly cookies
- Environment variable configured admins

---

## Integrations

### Telegram

- **Mini App SDK** - Native integration
- **WebApp API** - User authentication
- **Bot Integration** - Notifications
- **Stars Payments** - In-app purchases

### TON Blockchain

- **TON Connect** - Wallet connection
- **Transaction Verification** - Payment confirmation
- **NFT Minting** - Reward distribution

### External Services

| Service | Purpose |
|---------|---------|
| Supabase | Database and authentication |
| Adsgram | Ad network integration |
| GitHub Actions | Scheduled tasks (cron jobs) |

---

## Scheduled Tasks

| Task | Schedule | Purpose |
|------|----------|---------|
| Daily Spin Reset | 00:00 UTC | Notify all users |
| Spin Reminder | Every 3 hours | Notify users who haven't spun |
| Weekly Leaderboard Reset | Monday 00:00 UTC | Process rewards, reset scores |
| TON Price Update | Every hour | Update exchange rate |
| Pending Purchase Cleanup | Daily | Remove stale transactions |
| Session Cleanup | Daily 04:00 UTC | Remove expired game sessions |

---

## Environment Variables

```env
# Database
NEXT_PUBLIC_SUPABASE_URL=
SUPABASE_SERVICE_ROLE_KEY=

# Telegram
TELEGRAM_BOT_TOKEN=
NEXT_PUBLIC_BOT_USERNAME=

# TON
TON_USD_PRICE=5.5
TON_MINTER_ADDRESS=
NEXT_PUBLIC_TON_CONNECT_MANIFEST_URL=

# Payments
STARS_TO_USD_RATE=0.013

# Admin
DASHBOARD_ADMINS=email:password
DASHBOARD_JWT_SECRET=

# Ads
NEXT_PUBLIC_ADSGRAM_BLOCK_ID=

# App
APP_URL=
CRON_SECRET=
```

---

---

## Support

For issues or feature requests, please contact the development team or submit via GitHub Issues.
