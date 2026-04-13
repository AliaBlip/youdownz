<div align="center">
██╗ ██╗ ██████╗ ██╗ ██╗██████╗ ██████╗ ██╗ ██╗███╗ ██╗███████╗
╚██╗ ██╔╝██╔═══██╗██║ ██║██╔══██╗██╔═══██╗██║ ██║████╗ ██║╚══███╔╝
╚████╔╝ ██║ ██║██║ ██║██║ ██║██║ ██║██║ █╗ ██║██╔██╗ ██║ ███╔╝
╚██╔╝ ██║ ██║██║ ██║██║ ██║██║ ██║██║███╗██║██║╚██╗██║ ███╔╝
██║ ╚██████╔╝╚██████╔╝██████╔╝╚██████╔╝╚███╔███╔╝██║ ╚████║███████╗
╚═╝ ╚═════╝ ╚═════╝ ╚═════╝ ╚═════╝ ╚══╝╚══╝ ╚═╝ ╚═══╝╚══════╝ 


</br>

<img src="https://img.shields.io/badge/node-%3E%3D18.0.0-339933?style=for-the-badge&logo=node.js&logoColor=white" alt="Node.js">
<img src="https://img.shields.io/badge/deployed%20on-vercel-000000?style=for-the-badge&logo=vercel&logoColor=white" alt="Vercel">
<img src="https://img.shields.io/badge/license-MIT-blue?style=for-the-badge" alt="License">
<img src="https://img.shields.io/badge/status-working-22c55e?style=for-the-badge" alt="Status">
<img src="https://img.shields.io/badge/PRs-welcome-ef4444?style=for-the-badge" alt="PRs">


**🎬 A free, fast, and no-bullshit YouTube downloader.**

**Paste. Click. Download. That's it.**



[🚀 Live Demo](https://youdownz.vercel.app) · [🐛 Report Bug](https://github.com/AliaBlip/youdownz/issues) · [☕ Saweria](https://saweria.co/tikdownz)



---

</div>



## `> preview.txt`
┌──────────────────────────────────────────────────────────────────┐
│ │
│ ▶ YouDownz [GitHub] [☕ Saweria] │
│ │
│ Download YouTube Videos │
│ Paste link, pilih format, download. Gampang banget. │
│ │
│┌──────────────────────────────────────┐ ┌──────────────┐ │
│ │ 🔗 Paste YouTube URL disini... │ │ Cari Video │ │
│ └──────────────────────────────────────┘ └──────────────┘ │
│ │
│ ┌──────────────────────────────────────────────────────────┐ │
│ │ ┌─────────┐ │ │
│ │ │▓▓▓▓▓▓▓▓▓│ Video Title Here │ │
│ │ │▓▓▓ ▶ ▓▓▓│ Channel Name │ │
│ │ │▓▓▓▓▓▓▓▓▓│ 3:45 • 1.2M views │ │
│ │ │▓▓▓▓▓▓▓▓▓│ │ │
│ │ └─────────┘ [⬇ Download Video] [🎵 Download Audio] │ ││ └──────────────────────────────────────────────────────────┘ │
│ │
│ 📋 Available Formats │
│ ┌──────────────────────────────────────────────────────────┐ │
│ │ VIDEO 720p (mp4) [Download] │ │
│ │ VIDEO 360p (mp4) [Download] │ │
│ │ AUDIO 128kbps (webm) [Download] │ │
│ └──────────────────────────────────────────────────────────┘ │
│ │
└──────────────────────────────────────────────────────────────────┘
<br/>

## `> features.md`

```diff
+ ✅ No ads, no popups, no tracking
+ ✅ Multiple video quality options (360p, 720p, etc.)
+ ✅ Audio-only download support
+ ✅ Mobile responsive
+ ✅ One-click deploy to Vercel
+ ✅ Auto-paste URL detection
+ ✅ Multiple fallback APIs (always works)
+ ✅ Dark mode by default (because we're not animals)
+ ✅ Zero dependencies on client side
+ ✅ Serverless API (Vercel Edge Functions)

> architecture.md
                    ┌─────────────────────────────────────────┐
                    │              CLIENT (Browser)           │
                    │                                         │
                    │  index.html ─── style.css ─── script.js │
                    └──────────────────┬──────────────────────┘
                                       │
                                       │  HTTP Request
                                       │  /api/download?action=info&url=...
                                       │  /api/download?action=download&url=...
                                       ▼
                    ┌─────────────────────────────────────────┐
                    │          VERCEL SERVERLESS API           │
                    │            api/download.js               │
                    │                                         │
                    │  ┌───────────────────────────────────┐  │
                    │  │  1. Extract Video ID from URL     │  │
                    │  │  2. Fetch info from oEmbed API    │  │
                    │  │  3. Try Invidious instances        │  │
                    │  │  4. Fallback to Cobalt API        │  │
                    │  │  5. Return direct download URLs   │  │
                    │  └───────────────────────────────────┘  │
                    └──────────┬──────────────┬───────────────┘
                               │              │
                    ┌──────────▼──────┐ ┌─────▼──────────────┐
                    │  INVIDIOUS API  │ │   COBALT API       │
                    │  (Primary)      │ │   (Fallback)       │
                    │                 │ │                     │
                    │ • inv.tux.pizza │ │ • api.cobalt.tools  │
                    │ • vid.puffyan.us│ │                     │
                    │ • + 2 more      │ │                     │
                    └─────────────────┘ └─────────────────────┘ </br>
> tree .
youdownz/
│
├── api/
│   └── download.js          # Serverless API handler
│
├── public/
│   ├── index.html            # Main page
│   ├── style.css             # Styles (dark theme)
│   └── script.js             # Client-side logic
│
├── package.json              # Dependencies
├── vercel.json               # Vercel deploy config
├── LICENSE                   # MIT License
└── README.md                 # You are here

> ./install.sh

Prerequisites
$ node --version
v18.0.0    # Required: >= 18.0.0

$ npm --version
9.0.0      # Any recent version

$ vercel --version
33.0.0     # Optional: for deployment


> Quick Start
# Clone the repo
$ git clone https://github.com/AliaBlip/youdownz.git

# Navigate to project
$ cd youdownz

# Install dependencies
$ npm install

# That's it. Now deploy or run locally.

> ./deploy.sh
# Install Vercel CLI globally
$ npm install -g vercel

# Login to your Vercel account
$ vercel login

# Deploy to production
$ vercel --prod

# Output:
# ✅ Production: https://youdownz.vercel.app

>  api-docs.md
Endpoints
text

GET /api/download
Parameters
Param	Type	Required	Description
action	string	✅	info | download | direct
url	string	✅	YouTube URL (encoded)
format	string	❌	video | audio (default: video)

> Example Request
# Get video info + available formats
$ curl "https://youdownz.vercel.app/api/download?action=info&url=https://youtube.com/watch?v=dQw4w9WgXcQ"

# Response:
{
  "success": true,
  "info": {
    "title": "Rick Astley - Never Gonna Give You Up",
    "author": "Rick Astley",
    "thumbnail": "https://img.youtube.com/vi/dQw4w9WgXcQ/hqdefault.jpg",
    "videoId": "dQw4w9WgXcQ",
    "duration": 212,
    "viewCount": 1500000000
  },
  "formats": [
    {
      "quality": "720p",
      "type": "video",
      "container": "mp4",
      "url": "https://...",
      "label": "🎬 720p (mp4)"
    },
    {
      "quality": "128kbps",
      "type": "audio",
      "container": "webm",
      "url": "https://...",
      "label": "🎵 Audio 128kbps (webm)"
    }
  ],
  "hasDirectLinks": true
}

# Get download link (video)
$ curl "https://youdownz.vercel.app/api/download?action=download&url=https://youtube.com/watch?v=dQw4w9WgXcQ&format=video"

# Response:
{
  "success": true,
  "download": {
    "url": "https://direct-download-link...",
    "quality": "720p",
    "method": "invidious"
  }
}

# Get download link (audio only)
$ curl "https://youdownz.vercel.app/api/download?action=download&url=https://youtube.com/watch?v=dQw4w9WgXcQ&format=audio"

# Error Response
{
  "error": "Invalid YouTube URL"
}

> how-it-works.md

# Pseudocode of the download flow

def handle_request(url, action, format):
    
    # Step 1: Parse the YouTube URL
    video_id = extract_video_id(url)        # "dQw4w9WgXcQ"
    
    if action == "info":
        # Step 2a: Get video metadata
        info = fetch_oembed(video_id)        # title, author, thumbnail
        formats = []
        
        # Step 3a: Try Invidious instances (round-robin)
        for instance in INVIDIOUS_INSTANCES:
            try:
                data = fetch(f"{instance}/api/v1/videos/{video_id}")
                formats = parse_formats(data)
                break                        # success, stop trying
            except:
                continue                     # try next instance
        
        return { info, formats }
    
    if action == "download":
        # Step 2b: Try to get direct download URL
        
        # Priority 1: Invidious (most reliable)
        result = try_invidious(video_id, format)
        
        # Priority 2: Cobalt API (fallback)
        if not result:
            result = try_cobalt(url, format)
        
        # Priority 3: Give up gracefully
        if not result:
            return error("No download source available")
        
        return { download: result }
