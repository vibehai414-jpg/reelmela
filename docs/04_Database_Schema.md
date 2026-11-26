# ReelMela — Database Schema (Firebase Firestore + Storage)

## Collections

### users
- uid: string (PK)
- name: string, photoURL: string, phone: string (private)
- instagramHandle: string (optional, user-entered, only revealed on match)
- city: string, age: number, is18Plus: boolean
- isPro: boolean, proUntil: timestamp
- meetOptIn: boolean, meetGenderPref: string
- createdAt, lastActiveAt

### events
- eventId: string (PK)
- title: string, description: string, coverURL: string
- city: string, location: string, lat/lng: geo (optional)
- startAt, endAt: timestamp, status: live | upcoming | ended
- organizerId: string (FK users), type: public | private
- joinCode / qrCode: string, maxCreators: number
- prizePool: number, sponsorName: string, sponsorLogoURL: string
- clipsCount: number, totalViews: number
- createdAt

### clips (subcollection under events OR top-level with eventId)
- clipId: string (PK)
- eventId: string (FK), uploaderId: string (FK users)
- videoURL: string (Storage), thumbnailURL: string, durationSec: number
- caption: string, allowAftermovie: boolean, allowMeet: boolean
- status: pending | approved | rejected | selected_for_aftermovie
- likesCount, viewsCount, watchTimeSec: number
- isProClip: boolean, createdAt

### collabReels
- reelId: string (PK)
- eventId: string, title: string, videoURL: string, thumbnailURL: string
- creatorIds: array<string> (all tagged), totalViews, totalLikes, totalShares
- earningsPool: number, status: draft | published | viral
- publishedAt, instagramPostURL: string (optional)

### aftermovies
- aftermovieId: string (PK)
- eventId: string, videoURL: string (free watermarked), videoURL_HD: string (PRO only)
- durationSec, clipIdsUsed: array<string>, credits: array<{userId, secondsUsed}>
- status: processing | ready | failed
- createdAt

### walletTransactions
- txnId: string (PK)
- userId: string, eventId / reelId: string, type: earning | withdrawal | pro_purchase
- amount: number, reason: string, status: pending | completed
- upiId: string (for withdrawal), createdAt

### matches (Meet)
- matchId: string (PK)
- eventId: string, userAId: string, userBId: string
- status: pending | matched | blocked
- likedAt, matchedAt, igRevealedAt: timestamp

### likes
- likeId: string, userId, targetType: clip | reel | meet_profile, targetId, createdAt

### reports
- reportId, reporterId, reportedUserId / clipId, reason, status: open | resolved, createdAt

## Storage Buckets (Firebase Storage / Cloudinary)
- /events/{eventId}/cover.jpg
- /clips/{eventId}/{clipId}.mp4
- /aftermovies/{eventId}.mp4
- /thumbnails/{clipId}.jpg

## Indexes Needed
- events by city + status + startAt
- clips by eventId + status + watchTimeSec desc
- collabReels by totalViews desc
