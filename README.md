# Video Dubber (XTTSv2 + M2M100 + Faster-Whisper)

Mobile & Web friendly video dubbing Space using:
- **ASR**: faster-whisper
- **Translate**: facebook/m2m100_418M (many-to-many)
- **TTS / Voice Clone**: Coqui **XTTS v2** (reference voice optional)
- **Mux**: moviepy + ffmpeg

**Features**
- Upload a video (mp4/mov/webm)
- Auto-detect source language, transcribe, translate to target language(s)
- Voice clone from a short reference audio (optional)
- Replace audio track and export a dubbed MP4
- Also export SRT subtitles

## Quick Start (Spaces)
1. Create a new Space → SDK: **Gradio** → Hardware: **CPU** (GPU recommended for speed)
2. Upload files: `app.py`, `requirements.txt`, `README.md` (this file)
3. Click **Deploy**. First build can take a while due to model downloads.
4. Test with a 15–30 sec clip first.

### Recommended Hardware
- CPU works for demos. For faster TTS/ASR, choose **A10G** GPU in Space **Settings → Hardware**.

## How it works
```mermaid
flowchart TD
  A[Upload Video] --> B[Extract Audio]
  B --> C[ASR: faster-whisper]
  C --> D[Translate: M2M100]
  D --> E[TTS: XTTS v2\n(optional voice clone)]
  E --> F[Replace Audio Track]
  F --> G[Dubbed MP4 + SRT]
