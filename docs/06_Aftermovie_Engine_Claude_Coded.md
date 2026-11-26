# ReelMela — Aftermovie Engine (Claude + Coded Videos, No VidRush)

Goal: Turn 50-200 raw clips from one event into ONE 2-3 min Aftermovie + ONE 30-sec Collab Reel, for ₹0.

## Pipeline (5 Steps)

Step 1: Collect
- All approved clips from Firestore -> download to /tmp/clips
- Metadata: uploaderId, duration, watchTime, likes, isPro

Step 2: Select (AI Logic, No ML needed for MVP)
- Sort by: (watchTime * 0.6 + likes * 0.4)
- PRO clips: Force-include, min 8 sec, place in first 15 sec
- Free clips: Take top 20-30 clips, max 6 sec each, ensure diversity (different uploaders)
- Total target: 120-180 sec for Aftermovie, 30 sec for Collab Reel

Step 3: Edit (Python + MoviePy + FFmpeg)
- Normalize: Resize to 1080x1920 (Reel) or 1920x1080 (Aftermovie), 30fps
- Add: Fade transitions, auto-captions (Whisper), background music (royalty-free from Pixabay), lower-third name: "@username - Harda Fest"
- Add: Intro 3 sec: "Harda College Fest | ReelMela" + Outro 3 sec: Credits + Sponsor logo
- Export: MP4 H.264, 1080p

Step 4: Upload
- Upload to Firebase Storage, save URL in aftermovies collection, set status=ready
- Notify all contributors: "Your Aftermovie is ready!"

Step 5: Post
- Admin downloads + posts to Instagram as Collab (manual in MVP, auto via Meta API in v2)

## Where to Run (Free)
- MVP: Google Colab (free GPU) — run notebook manually after event
- V2: Cloud Run / Firebase Functions (pay per run, ~₹5 per aftermovie)

## Claude Prompt to Generate Engine (Copy-Paste)
> Make me a Python script using MoviePy that takes a folder of MP4 clips from one event and creates a 2-minute Aftermovie.
> Input: /clips folder with metadata.json (clipId, uploader, likes, watchTime, isPro)
> Logic: PRO clips first 15 sec guaranteed, top clips by watchTime, max 6 sec per clip, total 120 sec.
> Add: Fade transitions, auto-captions from filename, background music from /music.mp3 at 20% volume, intro/outro text.
> Export: 1080x1920 MP4, no watermark, save to /output/aftermovie.mp4

## Cost Comparison
- VidRush: $99/mo, 45 min limit
- ReelMela Engine: ₹0 (Colab) + ₹0 (MoviePy) + Music free
