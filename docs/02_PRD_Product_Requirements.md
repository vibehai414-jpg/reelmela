# ReelMela — Product Requirements Document (PRD)

## A. User Personas
1. **Aarav, 19, Harda College Student:** Goes to fest, shoots dance reel, wants fame + meet people. Will pay ₹99 for guaranteed spot.
2. **Priya, 21, Indore:** Goes to Garba, shy, wants to find boy she saw. Needs safe Meet.
3. **Rohan, Organizer:** College fest organizer. Wants free promotion + aftermovie for next year poster. Will pay ₹5k-20k.
4. **Cafe Owner, Harda:** Wants local brand on Aftermovie. Will sponsor ₹3k-10k.

## B. MVP Scope (Week 1-2) — MUST HAVE
- Auth: Google Login, Phone OTP (Firebase Auth), Age gate 18+ for Meet, 16+ for rest
- Profile: Name, photo, Instagram handle (optional, user-entered), city, bio
- Events: Create Event (name, date, location, cover, type: Public/Private, max creators), Join Event (QR + Link), Event Detail Page (clips grid, leaderboard, Join button, countdown)
- Upload: Video 15-30 sec (MVP allows up to 60 sec), caption, allow-in-aftermovie toggle, compression client-side, upload progress
- Reels Feed: Vertical swipe, like, comment, share, save, filter pills, Earn badge, Join Event CTA
- Aftermovie Page: Player mock + Download (Free watermarked, PRO HD no watermark), credits list
- Wallet: Balance, transaction history, split breakdown, Withdraw via UPI (show fake in MVP, real in v2)
- Leaderboard: By clip watch-time + likes
- Meet (MVP basic): Opt-in toggle, view profiles from same event, Like, Mutual Match -> Reveal IG ID
- Admin: Approve events, flag clips, manual aftermovie trigger

## C. V2 (Month 2) — SHOULD HAVE
- Auto-Aftermovie generation (AI selects best clips)
- PRO checkout (Razorpay)
- Sponsor dashboard for organizers
- Push notifications: Your clip selected, Match, Payout
- Search: Events by city, hashtag
- Report/Block, moderation queue

## D. V3 (Month 3+) — NICE TO HAVE
- Live event wall (real-time slideshow at venue)
- AI Face Fix (brightness, stabilization)
- Multi-language: Hindi + English
- Brand marketplace

## E. User Flows
### Flow 1: Join & Upload
Home -> Events -> Event Detail -> Join -> Upload -> Success Toast "You're in the collab!" -> See clip in grid

### Flow 2: Watch & Earn
Reels Feed -> Watch Collab Reel -> Like -> Tap Earn badge -> Wallet shows split

### Flow 3: Meet
Event Detail -> Turn ON Meet -> After Event -> Meet Tab shows profiles from same event -> Like -> Mutual -> Match screen reveals IG IDs

### Flow 4: PRO Purchase
Aftermovie Page -> "Your clip not selected? Go PRO to guarantee" -> Pay ₹99 -> Guaranteed in next cut

### Flow 5: Organizer Creates Event
+ Create Event -> Fill form -> Get QR + Share Link -> Share on WhatsApp/Insta -> See live uploads

## F. Non-Functional Requirements
- Video upload < 100MB, support 720p/1080p, H.264 MP4
- Feed loads in <2 sec on 4G
- Works on low-end Android (2GB RAM)
- Offline: Cache feed thumbnails
- Privacy: No location tracking without permission, no IG ID shown before match
