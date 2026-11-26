# ReelMela — UI/UX Screens (Mobile-First, 430px shell)

Design System:
- Theme: Dark #0A0A0F, Cards #16161F, Accent Gradient: Orange #FF6A00 -> Pink #FF2E63 -> Purple #7C3AED
- Font: Inter / Plus Jakarta Sans, Bold headings
- Bottom Nav: Reels (Home) | Events | Upload (+) Center | Meet | Wallet
- Top Bar: Logo ReelMela + Location (Harda, MP) + Search + Notifications

## Screens List (12 Screens)

1. **Splash / Onboarding:** Logo, "Don't post alone", 3 slides: Collab -> Aftermovie -> Earn, CTA Login with Google
2. **Login:** Google + Phone OTP, Age checkbox, City picker
3. **Reels Feed (Home):** Vertical full-screen reel, right actions (Like, Comment, Share, Save), bottom caption + Earn badge + Join Event button, top filter pills: For You | Near You | Collab Reels | Aftermovies | Meet, swipe hint
4. **Events List:** Search, City filter, Cards: Cover, Live badge, Clips count, Prize pool, Join button, 3 sample events: Harda College Fest (Live), Indore Garba Night, Bhopal Music Fest
5. **Event Detail:** Banner, Info, Join / Joined, Upload CTA, Leaderboard (Top 5), Clips Grid (6 thumbnails), Meet toggle, Aftermovie teaser
6. **Upload:** Drag/drop or pick video, preview, caption input (prefilled event hashtag), toggle "Allow in Aftermovie", toggle "Allow in Meet", Upload button, progress bar
7. **Aftermovie Page:** Player, Title, "Made from 128 clips by 42 creators", Download Free / PRO HD, Share, Credits list with PRO badges
8. **Wallet:** Balance ₹1,250, Breakdown list, Withdraw via UPI button, How earnings work explainer, PRO upsell
9. **Meet Tab:** Header "People from Harda College Fest", Cards: Photo, Name, Age, Clip thumbnail, Like / Pass, Match screen: "It's a Match! @insta_id revealed", Safety note
10. **Profile:** My clips, My earnings, My events, PRO status, Edit IG handle, Settings
11. **Create Event (Organizer):** Form: Name, Date, Location, Cover, Type, Max creators, Sponsor slot, Generate QR
12. **PRO Paywall:** Comparison table Free vs PRO, ₹99/event, ₹199/month, Razorpay button, Benefits list

## Interaction Rules
- Join toggles to Joined
- Like toggles heart + count +1
- Upload shows success toast
- Filter pills (Near You etc) filter feed in v2
- All buttons have haptic-like scale animation

## Prototype Reference
Current prototype covers: Reels Feed, Events, Upload, Aftermovie, Wallet, Meet basics.
