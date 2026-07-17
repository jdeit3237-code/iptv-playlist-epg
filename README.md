IPTV XMLTV Playlist

This repository contains filtered_us.xml.gz — a gzipped XMLTV file with validated HLS streams and placeholder EPG.

How to publish on GitHub Pages (recommended):

1) Create a new GitHub repository (via web UI) named "iptv-playlist-epg" (or any name).
2) On your machine, in this folder, run:

   cd iptv-playlist-epg
   git remote add origin https://github.com/<YOUR_USER>/iptv-playlist-epg.git
   git branch -M gh-pages
   git push -u origin gh-pages

3) After push, the file will be served by GitHub Pages at:

   https://<YOUR_USER>.github.io/iptv-playlist-epg/filtered_us.xml.gz

Alternative: Use the GitHub CLI to create & push in one step (if gh is installed):

   cd iptv-playlist-epg
   gh repo create <YOUR_USER>/iptv-playlist-epg --public --source=. --push --branch gh-pages

Notes:
- The raw GitHub URL is also available at:
  https://raw.githubusercontent.com/<YOUR_USER>/iptv-playlist-epg/gh-pages/filtered_us.xml.gz
- If you prefer the main branch, enable Pages from the main/docs folder in repo settings.

Security & usage:
- This makes the file publicly accessible. If you need restricted access, use S3 presigned URLs or a private hosting solution.

