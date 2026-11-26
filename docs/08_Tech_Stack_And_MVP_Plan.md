# ReelMela — Tech Stack & MVP Build Plan (1 Week)

## Tech Stack (Free Tier First)
- Frontend: React Native (Expo) for App OR Next.js PWA for Web MVP (Recommended: Start with PWA, cheaper, no Play Store approval)
- Backend: Firebase (Auth, Firestore, Storage, Functions) — Free tier covers MVP
- Video Processing: Python + MoviePy + FFmpeg on Google Colab (MVP) -> Cloud Run (V2)
- Payments: Razorpay (India, UPI) — Test mode in MVP
- Notifications: Firebase Cloud Messaging
- Analytics: Firebase Analytics + Mixpanel free
- Design: Figma (free) -> Tailwind CSS

## Why PWA First?
- No Play Store wait, share link on WhatsApp, works on any Android
- Later wrap same code into Play Store app via Capacitor

## MVP Build Timeline
Day 1: Setup Firebase, Auth, Profile, Events CRUD
Day 2: Upload (video compress + Storage), Event Detail + Clips Grid
Day 3: Reels Feed UI (static + like), Aftermovie Page UI
Day 4: Wallet UI + Fake Split Logic, Leaderboard
Day 5: Meet UI (Opt-in, Like, Match), PRO Paywall UI (no real payment)
Day 6: Aftermovie Engine in Colab, test with 10 sample clips
Day 7: Test with 5 friends at mock event, fix bugs, share prototype link

## Claude Workflow to Build
- Use Claude to generate each screen: "Make React Native screen for ReelMela Reels Feed..."
- Use Claude to generate backend: "Make Firebase Function for split calculation..."
- Use Claude to generate Aftermovie script (see File 06)

## Cost to Build MVP
- Firebase: ₹0 (free tier)
- Colab: ₹0
- Domain: ₹800/yr (reelmela.in)
- Razorpay: 2% per transaction, no setup
- Total MVP: < ₹1,000

## Cost to Run Per Event (100 clips)
- Storage: ~10GB video = ~₹200 (Firebase) or ₹0 (Cloudinary free 25GB)
- Processing: Colab free, Cloud Run ~₹50
- Total: ₹250 per event, Revenue: ₹10k-25k per event
