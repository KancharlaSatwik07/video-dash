# 🎬 DASH Media Encoder & Streaming Pipeline

A Python-based media processing pipeline that downloads videos from multiple platforms, converts them into **MPEG-DASH** format with **multiple audio tracks**, extracts subtitles, generates a **JW Player HTML page**, and uploads everything to a remote server via **SFTP**.

> Built for fast deployment of adaptive streaming content with automatic HTML player generation.

---

## ✨ Features

- 📥 Download videos from multiple sources using `yt-dlp`
- 🎞️ Convert videos to MPEG-DASH (.mpd)
- 🔊 Preserve and package multiple audio tracks
- 💬 Extract subtitle tracks (VTT)
- 📺 Generate a responsive JW Player streaming page
- 🎭 Optional TMDB integration for Movies & TV Shows
- 🖼️ Automatically fetch:
  - Poster
  - Backdrop
  - Overview
  - Genres
  - Episode information
- ☁️ Upload generated files to a remote SFTP server
- 🧹 Automatic cleanup after upload

---

## Supported Sources

This project supports almost every website supported by **yt-dlp**, including:

- YouTube
- Vimeo
- Facebook
- Instagram
- TikTok
- Twitch
- X (Twitter)
- Dailymotion
- Google Drive
- Direct MP4/MKV/WebM URLs
- HLS (.m3u8)
- and hundreds of other supported platforms

---

## Project Workflow

```text
Video URL
      │
      ▼
Download Video
      │
      ▼
Extract Audio Tracks
      │
      ▼
Extract Subtitles
      │
      ▼
Convert Video → MPEG-DASH
      │
      ▼
Generate HTML Player
      │
      ▼
(Optional) Fetch TMDB Metadata
      │
      ▼
Upload via SFTP
      │
      ▼
Streaming Ready
```

---

# Technologies Used

- Python
- FFmpeg
- yt-dlp
- Paramiko
- Google Drive Downloader
- JW Player
- TMDB API
- MPEG-DASH

---

# Installation

Install FFmpeg and required Python packages.

```bash
sudo apt update
sudo apt install ffmpeg -y

pip install yt-dlp
pip install paramiko
pip install gdown
pip install requests
```

or

```bash
pip install -r requirements.txt
```

---

# Usage

Run the notebook or Python script.

You'll be asked for:

```
Enter Video URL:
```

Example

```
https://youtu.be/example
```

The application will automatically:

- Download media
- Encode DASH
- Extract subtitles
- Generate HTML player
- Upload to server
- Display streaming links

---

# Generated Files

```
output.mpd
init-stream0.m4s
chunk-stream*.m4s
audio*.m4a
subtitle*.vtt
stream.html
```

---

# TMDB Integration

Supports both:

### Movies

Search by:

- Movie Name
- TMDB ID

Automatically fetches:

- Poster
- Backdrop
- Description
- Release Date
- Genres

---

### TV Shows

Supports:

- TV Search
- Season Selection
- Episode Selection

Automatically updates the generated player page with episode information.

---

# HTML Player

The generated HTML includes:

- Responsive Design
- JW Player
- Adaptive DASH Streaming
- Subtitle Selection
- Playback Speed Controls
- Netflix-style Theme
- Poster Artwork
- Metadata

---

# Configuration

Update these variables before running:

```python
SFTP_HOST =
SFTP_PORT =
SFTP_USERNAME =
PRIVATE_KEY_PATH =
REMOTE_BASE_PATH =
BASE_URL =
TMDB_API_KEY =
```

---

# Folder Structure

```
project/

│
├── users/
│
├── output.mpd
├── stream.html
├── subtitles/
├── audio/
├── video/
│
└── DASH_MAIN.ipynb
```

---

# Requirements

- Python 3.10+
- FFmpeg
- yt-dlp
- Paramiko
- Requests
- gdown

---

# Notes

- Uses H.264 encoding for maximum compatibility.
- Automatically converts unsupported codecs when required.
- Generates adaptive streaming output.
- Supports multiple language audio tracks.
- Supports subtitle extraction.

---

# Future Improvements

- DRM Packaging (Widevine/FairPlay/PlayReady)
- HLS Output
- Automatic Thumbnail Generation
- REST API
- Docker Support
- Web Dashboard
- Batch Encoding
- Cloud Storage Support (AWS S3 / Cloudflare R2)

---

# Disclaimer

This project is intended for educational and authorized media processing purposes only.

Users are responsible for ensuring they have the necessary rights and permissions to download, encode, upload, and distribute any content processed using this software.

---

# Author

**Satvik**

GitHub: https://github.com/yourusername

---

## ⭐ If you found this project useful, consider giving it a Star.
