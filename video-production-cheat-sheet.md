# Video Production Cheat Sheet

*One-page quick reference. Full detail: [video-production-best-practices.md](video-production-best-practices.md)*

## Video
| | |
|---|---|
| Capture res | **1920×1080 min** (2560×1440/4K for dense text, downscale in export) |
| Aspect | **16:9** |
| Frame rate | **30fps** (60fps only for live interaction) |
| Display scaling | **100%** during capture |
| Delivery | **H.264 MP4**, 1080p; keep 4K/uncompressed master |

## Screen capture
- Recording window sized to a clean **16:9**, no maximized multi-monitor spans
- Terminal/editor font **16–18pt min**
- Cursor highlight **on**
- Hide bookmarks bar, extensions, extra tabs
- **Demo account only** — check history, autofill, file names, terminal history for real creds/emails first
- Long waits (installs, builds): record real-time once → **speed-ramp 2–4× in edit**, never jump-cut

## Voice-over
| | |
|---|---|
| Mic | External cardioid, 6–12" off-axis, pop filter |
| Format | **WAV, 48kHz/24-bit** (never record straight to MP3) |
| Loudness | **-16 LUFS**, true peak ≤ -1 dBTP |
| Pace | **150 wpm** general / **130 wpm** dense technical steps |
| Room tone | Grab **5s of silence** at start of every session |
| File naming | `<script-slug>_<scene#>_<take>.wav` — one file per scene |
| Retakes | Re-read the full sentence, never a single word |

## On-camera speaker
- Use for **cold open + closing CTA**; voice-over alone is fine mid-video
- Eyes on **upper-third** gridline, small headroom, key light 45° + fill
- No window/backlight behind presenter
- **PiP size:** 18–22% of frame width, corner-placed, 8–12px safe margin
- Camera audio **never** used — sync external mic audio in post
- Name lower-third **once**, first appearance only, 3–4s

## On-screen text
- Title-safe area: **90%** (5% margin all sides)
- Lower thirds: **3s min** on screen, **1s min** after VO reference ends
- Caption/lower-third type: **32px min** at 1080p

## Captions
- Ship real captions (burned-in or .srt/.vtt) — **don't** rely on auto-captions alone
- **≤20 chars/sec**, max 2 lines on screen
- White text, ≥60% opacity dark background bar

## File delivery
- Folders: `/raw` `/project` `/exports` `/assets`
- Naming: `<script-slug>_v<version>_<resolution>.mp4`
- Dedicated **1280×720 thumbnail** export — never auto-selected
- Keep raw footage/audio **1 release cycle minimum** after publish

## Before you publish
- [ ] No real creds / tokens / emails / personal paths on screen
- [ ] Audio ~-16 LUFS, no clipping
- [ ] Captions accurate on technical terms (packages, commands, URLs)
- [ ] URLs/commands re-verified against current live docs
- [ ] Standard title card / lower third / end card templates used
- [ ] Watched full-through on desktop **and** phone-width
- [ ] Thumbnail exported and legible small
