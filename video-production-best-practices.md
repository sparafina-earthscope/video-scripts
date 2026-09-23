# Video Production Best Practices

**Scope:** Technical and editorial standards for GeoLab / EarthScope tutorial and explainer videos (screen-capture + narration, with or without an on-camera presenter).
**Applies to:** Anyone recording, editing, or reviewing video from a script in this repo.

---

## 1. Recording resolution & aspect ratio

| Setting | Standard | Notes |
|---|---|---|
| Capture resolution | **1920×1080 (1080p)**, minimum | Record at the highest resolution your source supports and downscale in export — never upscale. If the source material (dense code, small UI text) needs extra legibility, capture at **2560×1440** or native Retina/4K and downscale to 1080p; this sharpens fine text after compression. |
| Aspect ratio | **16:9** | Standard for YouTube, docs embeds, and conference-room displays. Don't record ultrawide or multi-monitor spans — crop to 16:9 before anything else happens in the edit. |
| Delivery resolution | **1080p (H.264)** minimum, **4K** master retained | Keep an uncompressed or lightly-compressed master; export the delivery copy separately so re-exports for other platforms don't recompress a recompression. |
| Frame rate | **30 fps** for screen capture / talking-head; **60 fps** only if the content includes real-time interaction (e.g., dragging a slider, live plotting) | Match your export frame rate to your capture frame rate — never convert 30fps footage to 60fps in post. |

## 2. Screen-capture setup

- **Browser/app window size:** Set the recording window to exactly **1920×1080** (or a clean 16:9 multiple) before you start — don't record a maximized window on a larger display and crop later; you lose resolution and risk misaligned safe margins.
- **OS/display scaling:** Set display scaling to **100%** during capture. Higher scaling (125%/150%) makes UI text crisper to the eye but throws off pixel-accurate crops and callout positioning.
- **Browser chrome:** Hide bookmarks bars, extensions, and unrelated tabs. Use a clean browser profile with no personal history/autofill visible in the address bar dropdown.
- **Cursor & clicks:** Enable cursor highlighting (a soft circle or color halo) and, where the recording tool supports it, click-ripple effects. Viewers lose the cursor constantly on screen capture without one.
- **Terminal/code font size:** **16–18pt minimum** in any terminal or editor being recorded. What's comfortably readable while sitting at the machine is usually too small once compressed into a 1080p video played at less than full screen.
- **Demo data & accounts:** Always record with a disposable/demo account. Before recording:
  - Clear browser history/autofill that could surface personal info in dropdowns.
  - Confirm file names, notebook contents, and terminal history (`history` / shell prompt) contain no real tokens, emails, or credentials.
  - Blur or replace any personal account name/email visible in account/profile screens, even on a demo account, so the pattern doesn't normalize showing real credentials on camera.
- **Pacing:** Type at a natural, deliberate pace — don't perform for the camera at full typing speed. Long waits (package installs, dependency resolution, server spin-up) should be **recorded in real time once**, then **speed-ramped (2–4×) in the edit**, not faked with a jump cut. Real output builds trust with a technical audience; a jump cut invites "what did they skip" doubt.

## 3. Voice-over capture

| Setting | Standard |
|---|---|
| Microphone | Cardioid USB or XLR condenser mic, 6–12 inches from mouth, off-axis from breath direction. Avoid laptop/webcam built-in mics — the noise floor and room reflections are audible even after cleanup. |
| Sample rate / bit depth | **48 kHz / 24-bit** |
| Format (raw capture) | **WAV**, uncompressed. Never record narration straight to MP3 — you lose headroom for cleanup and normalization. |
| Loudness target (delivery) | **-16 LUFS** integrated (streaming/web standard), true peak ≤ **-1 dBTP** |
| Noise floor | Record a **5 seconds of room tone** (silence) at the start of every session — needed for noise-reduction profiling in post, and as a safety cutaway. |
| Environment | A room with soft furnishings (carpet, curtains, a closet full of clothes) beats a "quiet" room with bare walls — hard surfaces cause audible reflections even without background noise. A pop filter is mandatory for any plosive-heavy script (lots of "p"/"b" sounds). |
| Pacing | **~150 words/minute** for narration read against on-screen action; slow to **~130 wpm** for dense technical steps (commands, flags, file contents) so viewers have time to read along. Leave a **0.5–1s pause** at sentence boundaries that coincide with a visual cut — it gives the edit somewhere to land. |
| File naming | `<script-slug>_<scene-number>_<take>.wav`, e.g. `temp-environments_03_take2.wav` — one file per scene, not one continuous take, so re-recording a single beat doesn't require a full re-read. |
| Retakes | Re-read a full sentence, never a single word — word-level punch-ins are audible even after tight editing, especially mid-sentence. |

## 4. Adding an on-camera speaker (presenter / talking head)

Use a presenter shot for the **cold open and the closing CTA** at minimum — a face at the start builds trust before the screen capture takes over, and a face at the end makes the call-to-action feel personal rather than templated. Pure voice-over is fine for the technical walkthrough in between.

| Setting | Standard |
|---|---|
| Camera resolution | **1080p minimum**, 4K preferred if it'll be cropped/repositioned in post |
| Framing | Head-and-shoulders, eyes roughly on the **upper third** gridline, small headroom above the head — not centered vertically |
| Lighting | One key light at 45°, one fill to soften shadows; avoid direct overhead light (raccoon-eye shadows) and avoid a bright window directly behind the presenter (silhouette) |
| Background | Simple, uncluttered, on-brand (a plain wall or blurred office is fine) — avoid busy bookshelves or anything that competes with lower-third text later placed over it |
| Eyeline | Camera at eye level, script/teleprompter positioned as close to the lens as possible so the presenter isn't visibly reading off to the side |
| Picture-in-picture (PiP) size | When compositing the presenter over screen capture (rather than full-frame), size the PiP to **18–22% of frame width**, bottom-left or bottom-right corner, with an **8–12px** safe margin from the edge — small enough not to block UI being demonstrated, large enough that facial expression still reads |
| PiP shape/treatment | A soft-rounded rectangle or circular crop with a **2–3px** brand-accent border reads as more polished than a hard-edged rectangle sitting directly on screen content |
| Audio sync | Always record presenter audio via the external mic setup in Section 3, not the camera's on-board mic — sync in post via a clap or slate rather than relying on camera audio for timing |
| Lower-third name tag | If it's the first time this presenter appears in the series, show a name/title lower third for **3–4 seconds** on first appearance only — don't repeat it in every video in the series |

## 5. On-screen text, lower thirds & callouts

- **Safe margins:** Keep all text, including lower thirds and captions, inside a **90% title-safe area** (5% margin on all sides) — some display/embed contexts crop edges.
- **Lower-third duration:** Minimum **3 seconds** on screen, minimum **1 second** after narration referencing it stops — don't cut a lower third the instant the sentence ends.
- **Type size:** Body captions/lower thirds no smaller than **32px** at 1080p export — smaller reads fine on a large monitor during editing and disappears on a phone screen.
- **Code/command callouts:** When highlighting a specific command or flag, prefer a **box or underline highlight** over a full re-typed on-screen graphic — it keeps the actual terminal/editor as the source of truth and avoids transcription typos.
- **Brand consistency:** Reuse one title-card template, one lower-third template, and one end-card template across the whole series — viewers should recognize a GeoLab video from its opening frame before any narration starts.

## 6. Captions & accessibility

- **Always ship captions** — either burned-in or as a separate `.srt`/`.vtt` file for platform-native captioning. Don't rely on auto-generated platform captions as the only version; review and correct technical terms (package names, flag names, product names) by hand.
- **Caption reading speed:** Target **≤ 20 characters/second** per caption line, max **2 lines** on screen at once.
- **Contrast:** White or near-white caption text on a semi-transparent dark bar (≥ 60% opacity) — never text directly over busy screen-capture content with no background.
- **Alt text / video description:** Every published video needs a one-paragraph written description covering what it shows — this also serves viewers who can't play audio/video at all.

## 7. File management & delivery

- **Folder structure per video:** `/raw` (uncut screen capture + raw audio), `/project` (editor project file), `/exports` (delivery renders), `/assets` (title cards, lower thirds, logos used).
- **Naming convention:** `<script-slug>_v<version>_<resolution>.<ext>`, e.g. `temp-environments_v2_1080p.mp4`.
- **Delivery formats:** **H.264 MP4** (broadest compatibility) as the primary delivery format; add **WebM (VP9)** if embedding directly on a web page where file size matters.
- **Thumbnail:** Export a dedicated 1280×720 thumbnail frame — don't let the platform auto-select a random frame. Include readable title text at a size legible in a small sidebar thumbnail.
- **Retention:** Keep the raw, uncut capture and raw audio for at least one full release cycle after publishing, in case a correction or re-cut is needed — don't delete raw footage as soon as the export ships.

## 8. Pre-publish QA checklist

- [ ] No real credentials, tokens, emails, or personal file paths visible in any frame
- [ ] Audio loudness measured at approximately -16 LUFS, no clipping (true peak ≤ -1 dBTP)
- [ ] Captions present and spot-checked for technical-term accuracy (package names, commands, URLs)
- [ ] All on-screen URLs/commands match the current live product/docs (re-verify against the source page, since UI and CLI syntax drift)
- [ ] Title card, lower thirds, and end card use the current shared templates
- [ ] Watched start-to-finish at delivery resolution on both a desktop and a phone-sized window
- [ ] Thumbnail exported and legible at small size

---

*Companion to the scripts in this repo — see [geolab-intro-script.md](geolab-intro-script.md) and [geolab-temporary-environments-script.md](geolab-temporary-environments-script.md) for examples of the format these standards apply to.*
