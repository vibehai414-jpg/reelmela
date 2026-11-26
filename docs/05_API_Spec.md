# ReelMela — API Spec (Firebase Functions / Node.js + Express)

Base URL: https://api.reelmela.app/v1
Auth: Firebase ID Token in header: Authorization: Bearer <token>

## Auth
POST /auth/google -> {uid, token}
POST /auth/phone/otp -> {otpSent}
POST /auth/phone/verify -> {uid, token}

## Users
GET /users/me -> profile
PATCH /users/me -> {name, city, instagramHandle, meetOptIn}
GET /users/:uid/clips -> list

## Events
GET /events?city=Harda&status=live -> [{event}]
POST /events -> {eventId} (organizer only)
GET /events/:eventId -> detail + clips + leaderboard
POST /events/:eventId/join -> {joined: true}
GET /events/:eventId/clips -> paginated clips
POST /events/:eventId/clips -> multipart video upload -> {clipId, videoURL}
DELETE /events/:eventId/clips/:clipId

## Reels Feed
GET /feed?filter=for_you|near_you|collab|aftermovie&page=1 -> [{reel}]
POST /feed/:reelId/like -> {liked, likesCount}
POST /feed/:reelId/comment -> {commentId}
POST /feed/:reelId/share -> {shareCount}

## Aftermovie
POST /events/:eventId/aftermovie/generate -> {jobId, status: processing} (admin / auto)
GET /events/:eventId/aftermovie -> {videoURL, videoURL_HD, credits}
GET /events/:eventId/aftermovie/download?quality=free|hd -> signed URL (HD requires PRO)

## Wallet
GET /wallet/balance -> {balance, pending}
GET /wallet/transactions -> [{txn}]
POST /wallet/withdraw -> {upiId, amount} -> {status}
POST /wallet/calculate-split -> (admin) triggers split by watch-time: earning = (userWatchTime / totalWatchTime) * pool

## PRO
POST /pro/purchase -> {plan: event|monthly, eventId} -> Razorpay order
POST /pro/webhook -> verify Razorpay, set isPro=true
GET /pro/status -> {isPro, proUntil}

## Meet
POST /meet/optin -> {meetOptIn: true}
GET /meet/:eventId/profiles -> [{profile, clipThumbnail}] (only if opt-in)
POST /meet/like -> {userBId} -> {matched: true/false}
GET /meet/matches -> [{match, revealedIgHandle if matched}]
POST /meet/block -> {blockedUserId}

## Admin / Moderation
GET /admin/reports -> [{report}]
POST /admin/clips/:clipId/approve|reject
POST /admin/events/:eventId/publish-reel

## Error Format
{ success: false, error: { code: "CLIP_TOO_LONG", message: "Clip must be 15-60 sec" } }

## Rate Limits
- Upload: 5 clips / event / user
- Like: 100 / min
- Feed: 60 req / min
