# Google Drive Audit — Free Tool by Pics.io

A free, client-side tool that scans your Google Drive metadata and shows you what's inside: file types breakdown, duplicates, largest files, and wasted storage space.

**Live tool:** https://crafty25.github.io/drive-audit/

## What it does

- Connects to your Google Drive via OAuth (read-only metadata, no file content access)
- Scans all files using Drive API v3
- Shows a dashboard with:
  - Total files & storage used
  - File type breakdown (pie chart)
  - Top 10 largest files
  - Top 10 duplicate groups (by md5 checksum)
  - Wasted space from duplicates
  - Personalized CTA to [Pics.io](https://pics.io) based on what was found

## Privacy

Scope used: `drive.metadata.readonly` — reads only file names, sizes, types, and checksums. **No file content is ever accessed or transmitted.** Everything runs in your browser.

## Run locally

No build step required. Just open `index.html` in a browser — or serve it with any static server:

```bash
npx serve .
# or
python3 -m http.server 8080
```

> Note: Google OAuth requires an authorized origin. For local testing, add `http://localhost:8080` (or whatever port you use) to your OAuth Client ID's authorized JavaScript origins in Google Cloud Console.

## Setup (for developers)

1. Create a project in [Google Cloud Console](https://console.cloud.google.com/)
2. Enable **Google Drive API**
3. Create an **OAuth 2.0 Client ID** (Web application)
4. Add your domain to Authorized JavaScript Origins
5. Replace `YOUR_GOOGLE_CLIENT_ID_HERE.apps.googleusercontent.com` in `index.html` with your Client ID

## Built with

- Vanilla HTML/CSS/JS — no framework, no build tools
- [Google Identity Services](https://developers.google.com/identity/gsi/web)
- [Google Drive API v3](https://developers.google.com/drive/api/v3/reference)
- [Chart.js](https://www.chartjs.org/) via CDN

---

Made by [Pics.io](https://pics.io) — Digital Asset Management for marketing and creative teams.
