# Florida Keys Live Feeds IPTV Channel

Live camera feeds from throughout the Florida Keys, including harbor views, beaches, parks, and marine monitoring feeds. Perfect for keeping tabs on weather, water conditions, and scenic views of the Keys.

## Quick Start

Add this playlist to your IPTV app (Max IPTV, VLC, etc.):

**Playlist URL:**
```
https://jdeit3237-code.github.io/iptv-playlist-epg/florida_keys_live.m3u
```

**EPG Guide URL:**
```
https://jdeit3237-code.github.io/iptv-playlist-epg/florida_keys_live.xml
```

### Max IPTV on Apple TV

1. Open **Max IPTV** app
2. Select **Playlists** → **Add Playlist**
3. Paste the playlist URL above
4. In **EPG Guides**, add the XML guide URL above
5. Feeds will appear organized by category

## Available Feeds

The channel includes live cameras from:

### Harbor & Marina (Key West)
- Key West Live Harbor Cam
- Key West Marina Live Feed
- Key West Historic Seaport

### Beaches & Resorts
- Marathon Resort Waterfront
- Islamorada Beach Resort Cam
- Key Largo Resort Beach

### Scenic Views
- Marathon Key Scenic View
- Islamorada Keys Waterfront
- Key Largo Northern Gateway

### Parks & Nature
- Bahia Honda State Park
- Dry Tortugas National Park
- Florida Keys Marine Monitoring

### Weather & Environmental
- Key West National Weather Service

### YouTube Channels
- **Florida Keys Webcams** - Multi-camera live feeds from throughout the Keys
- **Seek Florida Keys** - Live exploration and tour feeds of the Keys

## Automatic Updates

The feed list is **automatically validated and updated every 6 hours** via GitHub Actions. This ensures:

✅ Dead feeds are quickly detected and replaced  
✅ New feed URLs are tested before deployment  
✅ Feeds stay current with minimal manual maintenance  

**Update Schedule:** 00:00, 06:00, 12:00, 18:00 UTC

## File Details

| File | Purpose | Refresh Rate |
|------|---------|--------------|
| `florida_keys_live.m3u` | Master playlist with all feeds | Every 6 hours |
| `florida_keys_live.xml` | EPG guide with 6-hour schedules | Every 6 hours |
| `florida_keys_provider.json` | Provider metadata | Every 6 hours |

## Feed Categories

Feeds are automatically organized by category:

- **Harbor** - Waterfront and harbor views
- **Marina** - Boat docks and marinas
- **Seaport** - Commercial seaport activity
- **Beach** - Beach and resort views
- **Waterfront** - Waterfront areas
- **Gateway** - Gateway communities
- **Scenic** - Scenic overlooks
- **State Park** - Florida state parks
- **National Park** - National parks
- **Marine** - Marine monitoring and research
- **Weather** - Weather service feeds

## Validation Process

Each feed is validated using lightweight HTTP HEAD requests:

1. Workflow checks accessibility of all feed URLs
2. Only responsive feeds are included
3. Failed feeds are removed automatically
4. Workflow logs available in repository Actions tab

## Troubleshooting

### Feeds Not Showing
- Check your internet connection
- Verify EPG XML URL is correctly added
- Try refreshing the playlist in your app

### Feed Goes Offline
- Feeds are monitored every 6 hours
- Unresponsive feeds are removed automatically
- Updates are pushed to GitHub Pages immediately

### Black/No Signal
- Some feeds may be slow to load
- Check feed status in your app's details
- Try a different feed from same category

### YouTube Feeds Not Playing
- Max IPTV may need YouTube support enabled
- YouTube streams are dynamic and may require internet connection
- Some IPTV apps have native YouTube support; others may need yt-dlp
- Try opening the YouTube link directly if feed doesn't load in app

## URLs for Different Platforms

**VLC Player:**
```
https://jdeit3237-code.github.io/iptv-playlist-epg/florida_keys_live.m3u
```

**Kodi:**
```
https://jdeit3237-code.github.io/iptv-playlist-epg/florida_keys_live.m3u
```

**Plex IPTV:**
```
https://jdeit3237-code.github.io/iptv-playlist-epg/florida_keys_live.m3u
```

## Legal & Disclaimer

- Feeds are sourced from public, tourism-friendly websites
- Content is provided for informational purposes
- Check local regulations before recording or rebroadcasting
- No guarantee of feed availability or quality
- Monitor usage to comply with website terms of service

## Last Updated

Automatically refreshed every 6 hours via GitHub Actions.

---

**Repository:** [jdeit3237-code/iptv-playlist-epg](https://github.com/jdeit3237-code/iptv-playlist-epg)  
**Hosted on:** GitHub Pages (gh-pages branch)  
**Automation:** GitHub Actions workflow - `update-florida-keys.yml`
