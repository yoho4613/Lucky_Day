# Lucky Day - Telegram Mini App

> **MVP Completed** - Play-to-Earn Web3 Gaming Platform

## Table of Contents
- [Overview](#overview)
- [Project Status](#project-status)
- [Core Features](#core-features)
- [Reward System](#reward-system)
- [Mini Games](#mini-games)
- [Level & Tier System](#level--tier-system)
- [Monetization](#monetization)
- [User Progression](#user-progression)
- [Technical Architecture](#technical-architecture)
- [Admin Dashboard](#admin-dashboard)
- [Integrations](#integrations)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)

---

## Overview

**Lucky Day** is a Web3-enabled gaming and reward platform built as a Telegram Mini App. Users play skill-based mini-games to earn rewards including CLUBS tokens, TON cryptocurrency, bonus spins, and exclusive NFTs.

### Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | Next.js 16, React 19, TypeScript, Tailwind CSS v4 |
| Backend | Next.js API Routes, Supabase (PostgreSQL) |
| Blockchain | TON Network, TON Connect |
| UI | Framer Motion, Radix UI, Lucide Icons |
| Audio | Howler.js |
| Authentication | Telegram WebApp API |
| Payments | Telegram Stars, TON Crypto |
| Languages | English, Korean, Japanese, Chinese, Russian |

---

## Project Status

### MVP Features (Completed)

- [x] 12 Skill-based mini-games
- [x] Daily spin system with server-side game selection
- [x] Weighted random reward distribution
- [x] Level system (300 levels, 10 tiers)
- [x] Premium membership with daily bonuses
- [x] TON wallet integration (TON Connect)
- [x] Telegram Stars & TON payments
- [x] Referral system with revenue sharing
- [x] Weekly leaderboard with prizes
- [x] Daily check-in rewards
- [x] Task system (social tasks)
- [x] Admin dashboard
- [x] Multi-language support (5 languages)
- [x] Ad integration (Adsgram)
- [x] Push notifications via Telegram Bot

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

### Available Games (11 Active + 1 Disabled)

| Game | ID | Icon | Type | Status |
|------|----|------|------|--------|
| Neon Pulse | timing | 🎯 | Timing | Active |
| Reflex Dodge | dodge | ⚡ | Reflex | Active |
| Cyber Switch | switch | 🧠 | Memory | Active |
| Neon Slider | slider | 🔢 | Puzzle | Active |
| One Line | oneline | ✏️ | Drawing | Active |
| Cross Road | crossroad | 🐔 | Arcade | Active |
| Neon Stack | stack | 🏗️ | Stacking | Active |
| Maze Escape | maze | 🧭 | Navigation | Active |
| Neon Hue | colormatch | 🎨 | Matching | Active |
| Neon Keys | pianotiles | 🎹 | Rhythm | Active |
| Memory Flip | memoryflip | 🧠 | Memory | Active |
| Neon Flow | connectlines | 🔗 | Puzzle | Disabled |

### Game Architecture

- **Server-side selection**: Game is randomly chosen on server to prevent manipulation
- **Session-based validation**: 5-minute timeout per session
- **Configurable properties**: Active status, difficulty, i18n keys, color themes
- **Legacy support**: Disabled games preserved in history

---

## Level & Tier System

### Tier Progression (10 Tiers)

| Tier | Name | Levels | Requirements |
|------|------|--------|--------------|
| 1 | Bronze | 1-29 | Starting tier |
| 2 | Silver | 30-59 | ~1,500 CLUBS |
| 3 | Gold | 60-89 | ~7,500 CLUBS |
| 4 | Platinum | 90-119 | ~27,500 CLUBS |
| 5 | Diamond | 120-149 | ~77,500 CLUBS |
| 6 | Master | 150-179 | ~177,500 CLUBS |
| 7 | Grandmaster | 180-209 | ~300,000 CLUBS |
| 8 | Legend | 210-239 | ~500,000 CLUBS |
| 9 | Mythic | 240-269 | ~800,000 CLUBS |
| 10 | Immortal | 270-300 | ~1,000,000+ CLUBS |

### Level Requirements

Level up requires both:
- **CLUBS earned** (from games, rewards, referrals)
- **Spins completed** (daily + bonus)

### Level Rewards

| Level Type | Base Reward | Premium Bonus |
|------------|-------------|---------------|
| Normal (1,2,3...) | CLUBS only | 2x CLUBS + Spins |
| Every 5th (5,10,15...) | CLUBS + Spins | 2x both |
| Every 10th (10,20,30...) | Higher CLUBS + Spins | 2x both |
| Tier Up (30,60,90...) | Major rewards | 2x both |

### Milestone Rewards

| Level | Base | Premium |
|-------|------|---------|
| 100 | 3,000 CLUBS + 5 Spins | 6,000 CLUBS + 10 Spins |
| 200 | 10,000 CLUBS + 10 Spins | 20,000 CLUBS + 20 Spins |
| 250 | 20,000 CLUBS + 15 Spins | 40,000 CLUBS + 30 Spins |
| 300 | 50,000 CLUBS + 30 Spins | 100,000 CLUBS + 60 Spins |

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

| Tier | Duration | Daily Spins | Daily CLUBS |
|------|----------|-------------|-------------|
| Bronze | 7 Days | +1 | 100 |
| Silver | 30 Days | +2 | 300 |
| Gold | 90 Days | +3 | 500 |

**Membership Benefits:**
- Extra daily spins (claimable via membership page)
- Daily CLUBS bonus
- **Premium level rewards** (2x base rewards)
- Stackable duration (multiple purchases extend membership)

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

| Day | CLUBS | Spins |
|-----|-------|-------|
| 1-6 | 50-100 | 0 |
| 7 (Weekly) | 500 | 1 |

**Features:**
- Daily consecutive login bonuses
- Progressive rewards for streaks
- Weekly bonus on day 7
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

## Project Structure

```
web/
├── app/                    # Next.js App Router
│   ├── api/               # API Routes (70+ endpoints)
│   │   ├── admin/         # Admin operations
│   │   ├── game/          # Game sessions
│   │   ├── level/         # Level rewards
│   │   ├── shop/          # Purchases
│   │   ├── user/          # User data
│   │   └── ...
│   ├── admin-portal/      # Admin dashboard pages
│   └── (main)/            # Main app layout
├── components/
│   ├── games/             # 12 mini-game components
│   ├── ui/                # Radix UI components
│   └── ...                # Feature components
├── lib/                   # Utilities & services
│   ├── games.ts           # Game configuration
│   ├── levelSystem.ts     # Level calculations
│   ├── rewards.server.ts  # Reward pool (server-only)
│   ├── tonConnect.ts      # TON wallet integration
│   └── ...
├── sql/                   # Database schemas
└── public/                # Static assets
```

---

## Getting Started

### Prerequisites

- Node.js 18+
- Supabase project
- Telegram Bot Token
- TON wallet (for payouts)

### Installation

```bash
# Clone repository
git clone <repo-url>
cd telegram_web3_project/web

# Install dependencies
npm install

# Set environment variables
cp .env.example .env.local
# Edit .env.local with your values

# Run development server
npm run dev
```

### Database Setup

1. Create Supabase project
2. Run SQL migrations from `web/sql/` in order:
   - `full_schema.sql` (base tables)
   - `game_sessions_schema.sql`
   - `level_config_schema.sql`
   - `membership_schema.sql`
   - `weekly_leaderboard_schema.sql`
   - Other schemas as needed

### Telegram Bot Setup

1. Create bot via [@BotFather](https://t.me/botfather)
2. Enable Web App mode
3. Set webhook URL to `/api/telegram/webhook`
4. Configure Mini App URL

---

## Roadmap

### Planned Features

- [ ] Tier-exclusive game modes (Silver+)
- [ ] Weekly challenges
- [ ] Achievement system
- [ ] NFT integration (rewards, profile badges)
- [ ] Tournament mode
- [ ] Social features (friends, guilds)

---

## License

Private - All rights reserved

---

## Support

For issues or feature requests, contact the development team or submit via GitHub Issues.
