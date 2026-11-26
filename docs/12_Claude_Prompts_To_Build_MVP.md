# ReelMela — Claude Prompts to Build MVP (Copy-Paste)

## Prompt 1: Frontend PWA
> Build me a mobile-first PWA for ReelMela using Next.js + Tailwind.
> Screens: Reels Feed (vertical swipe), Events List, Event Detail, Upload, Aftermovie, Wallet, Meet, Profile.
> Design: Dark theme, orange-pink gradient, bottom nav: Reels | Events | Upload (+) | Meet | Wallet.
> Use dummy data for Harda College Fest, 42 creators, 1.2M views. Make Like button interactive.

## Prompt 2: Backend
> Make Firebase Functions backend for ReelMela.
> Collections: users, events, clips, collabReels, aftermovies, walletTransactions, matches.
> APIs: Create event, Join event, Upload clip, Get feed, Like, Calculate split by watchTime, Meet like/match.
> Use Node.js + Express, Firebase Admin SDK.

## Prompt 3: Aftermovie Engine
> [See File 06 for full prompt]

## Prompt 4: Database
> Generate Firestore security rules for ReelMela: Users can read public events, only upload to events they joined, only read own wallet, Meet profiles only if opt-in.

## Prompt 5: Pitch + Content
> Write me a 45-sec Instagram Reel script for ReelMela in Hinglish: "I went to event, posted reel, 200 views... What if we all upload together?"
> Also write WhatsApp message to convince college organizer in Harda to let me make free Aftermovie.

## How to Use
- Paste one prompt at a time in Claude, get code, test, then next prompt.
- Don't ask Claude to build everything in one go — it will break. Build screen by screen.
