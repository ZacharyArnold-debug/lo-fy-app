## 🧩 GitHub Issue Breakdown for Lo-Fy Production-Ready Expansion

---

### 🔊 Epic: Audio Processing Engine

**Issue #1 – File Validation Middleware**
- Accept only `.mp3` and `.wav`
- Max size: 10MB
- MIME-type check + error response
- [ ] Backend handler in `/upload`
- [ ] Return clear error messages on failure

**Issue #2 – Normalize Input Audio**
- Normalize volume levels to consistent output
- Use `pydub` or `librosa`
- [ ] Normalize audio file after validation
- [ ] Integrate into processing pipeline

**Issue #3 – Apply Reverb Filter**
- Simulate room reverb (preset)
- Can use convolution or `ffmpeg`
- [ ] Add toggle for reverb (on/off)
- [ ] Use default room-style impulse

**Issue #4 – Slow Down Tempo**
- Reduce tempo to 0.8x (configurable)
- Use `librosa.time_stretch()` or `ffmpeg`
- [ ] Optional slider: 0.6x–1.0x
- [ ] Integrate with main processing route

**Issue #5 – Vinyl Crackle Overlay**
- Overlay static/hiss track on processed audio
- Use preloaded `.wav` file for texture
- [ ] Add adjustable intensity (Low/Med/High)
- [ ] Mix in background at selected level

**Issue #6 – Export MP3 Output**
- Convert final audio to MP3
- Save temporarily in server/cloud
- [ ] Set unique filename
- [ ] Link to download with TTL

**Issue #7 – Generate 30-sec Preview**
- Clip start of processed audio
- Downsample for preview playback
- [ ] Create `/preview/:id` endpoint
- [ ] Auto-delete preview after session

**Issue #8 – TTL Cleanup Job**
- Remove files older than 60 mins
- Works on both full + preview tracks
- [ ] Cron job or async worker
- [ ] Logs total deleted per run

---

### 🧑‍🎤 Epic: Music Source Integration

**Issue #9 – Embed Royalty-Free Tracks UI**
- Section: “Try With Our Sample Tracks”
- Use Pixabay, FMA, Chosic, etc.
- [ ] Grid layout with play & import buttons
- [ ] Attribution note or tooltip

**Issue #10 – Add Track via URL or Source API**
- Let users pull tracks from legal libraries
- [ ] Paste URL or import via dropdown
- [ ] Fetch metadata + auto-apply licensing label

---

### 🔐 Epic: Authentication & Account Features

**Issue #11 – Google OAuth Setup**
- Login/logout with Firebase/Supabase
- [ ] Button component + auth hook
- [ ] Store basic profile (email, name)

**Issue #12 – Save Track History (Last 5)**
- List user's processed tracks after login
- [ ] Dashboard component with list view
- [ ] Download & delete options

**Issue #13 – Generate Shareable Track URLs**
- `/track/:id` pages with playback
- [ ] Signed URL with expiry or auth check
- [ ] Optional: share via Twitter, Discord, etc.

---

### ☁️ Epic: Secure File Handling

**Issue #14 – Connect to Cloud Storage**
- Use Cloudflare R2, AWS S3, or similar
- [ ] Store preview + final audio files
- [ ] TTL metadata support

**Issue #15 – File Upload Handling with Presigned URLs**
- Securely allow frontend-to-storage uploads
- [ ] Generate presigned POST/PUT URLs
- [ ] Validate on backend

**Issue #16 – Track File Cleanup via Job**
- Part of issue #8 or separate script
- [ ] Add server logs on cleanup success/failure

---

### 📈 Epic: Analytics & Monitoring

**Issue #17 – Frontend Analytics Setup**
- Use PostHog, Umami, or Plausible
- [ ] Track page views, preset usage
- [ ] Track clicks on download/share

**Issue #18 – Error Logging & Playback Failures**
- Track when preview/download fails
- [ ] Log error type + user ID (if logged in)
- [ ] Optional: retry logic

---

### 🎨 Epic: UI/UX Polish

**Issue #19 – Mobile Responsiveness & UX**
- Make all components mobile-friendly
- [ ] Stacking layout on narrow screens
- [ ] Responsive sliders/buttons

**Issue #20 – Add Spinner, Error Toasts, and Load States**
- Improve perceived performance
- [ ] Spinner on upload/process
- [ ] Toasts for success/fail actions

**Issue #21 – Branding: Logo, Favicon, Colors**
- Match dark lo-fi aesthetic
- [ ] Add logo to nav
- [ ] Style presets & download section with theme colors