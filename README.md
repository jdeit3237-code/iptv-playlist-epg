# Filtered US IPTV

**Validated US IPTV playlists with matching EPG guides, organized by 16 categories, automatically updated daily via GitHub Actions.**

## Overview

This repository contains:
- **1,000+ validated US IPTV streams** (public/free sources)
- **16 category-organized playlists** (News, Sports, Kids, Family, Entertainment, etc.)
- **Category-specific XMLTV EPG guides** for TV schedule display
- **Automated daily updates** via GitHub Actions (lightweight HEAD checks to validate stream availability)

All files are hosted on GitHub Pages and available via direct URLs for import into IPTV apps like Max IPTV.

## Quick Start

### Add Playlists to Max IPTV

Go to **IPTV Providers** → **Add Playlist**, then add each category:

| Category | Playlist URL | EPG URL |
|----------|--------------|---------|
| Entertainment | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_entertainment.m3u | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_entertainment.xml |
| Other | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_other.m3u | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_other.xml |
| News | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_news.m3u | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_news.xml |
| Family | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_family.m3u | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_family.xml |
| Sports | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_sports.m3u | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_sports.xml |
| Kids | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_kids.m3u | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_kids.xml |
| Education | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_education.m3u | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_education.xml |
| Religion | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_religion.m3u | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_religion.xml |
| Lifestyle | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_lifestyle.m3u | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_lifestyle.xml |
| Comedy | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_comedy.m3u | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_comedy.xml |
| Cooking | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_cooking.m3u | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_cooking.xml |
| Government | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_government.m3u | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_government.xml |
| Music | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_music.m3u | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_music.xml |
| Fishing | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_fishing.m3u | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_fishing.xml |
| SciFi | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_scifi.m3u | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_scifi.xml |
| International | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_international.m3u | https://jdeit3237-code.github.io/iptv-playlist-epg/filtered_us_international.xml |

**Steps in Max IPTV:**
1. Open Settings → IPTV Providers
2. Click "Add Playlist"
3. Enter playlist name (e.g., "Entertainment")
4. Paste the Playlist URL above
5. Enter the matching EPG URL
6. Save and refresh

## File Structure

```
.
├── filtered_us.m3u                 # Full US playlist (all channels, unfiltered)
├── filtered_us.xml                 # Full EPG (all channels)
├── filtered_us_[category].m3u      # Category playlists (16 files)
├── filtered_us_[category].xml      # Category EPG guides (16 files)
├── iptv_provider.m3u               # Meta-playlist (all categories)
├── filtered_us_provider.json        # Provider JSON (alternative format)
└── .github/workflows/
    └── update-playlists.yml        # GitHub Actions automation
```

## Automatic Updates

**Scheduled Updates:**
- Runs daily at **00:00 UTC** (adjust in `.github/workflows/update-playlists.yml` if needed).
- Fetches the latest iptv-org US playlist.
- Performs lightweight **HEAD checks** on each stream to verify availability.
- Regenerates `.m3u` and `.xml` files with current working streams.
- Automatically commits and pushes updates to `gh-pages` branch.
- Deployed to GitHub Pages within seconds of commit.

**View Workflow Status:**
Go to your GitHub repo → **Actions** → **Update IPTV Playlists** to see run history and logs.

**Manual Trigger:**
You can manually run the workflow anytime via the Actions tab → "Run workflow".

## How Validation Works

1. **Download**: Fetches iptv-org's public US playlist (https://raw.githubusercontent.com/iptv-org/iptv/master/streams/us.m3u).
2. **Filter**: Keeps only HTTP/HTTPS stream URLs (removes RTMP, UDP, etc.).
3. **Check**: Performs lightweight HEAD requests (with small GET fallback) on each URL (20 concurrent, 10-second timeout).
4. **Output**: Writes only URLs that respond with HTTP 200 and valid HLS/M3U8 signatures.
5. **Categorize**: Auto-assigns channels to 16 categories based on keywords (e.g., "cnn" → News, "disney" → Kids).
6. **Generate**: Creates category playlists and EPG guides with unique channel IDs for EPG mapping.

## Categories Included

- **Entertainment** (342 channels)
- **Other** (371 channels)
- **News** (102 channels)
- **Family** (65 channels)
- **Sports** (40 channels)
- **Kids** (38 channels)
- **Education** (15 channels)
- **Religion** (17 channels)
- **Lifestyle** (9 channels)
- **Comedy** (9 channels)
- **Cooking** (10 channels)
- **Government** (7 channels)
- **Music** (7 channels)
- **Fishing** (4 channels)
- **SciFi** (4 channels)
- **International** (2 channels)

## Important Notes

- **Stream Availability**: Streams are public/free sources provided by iptv-org. Some may go offline; the automated daily checks help keep the lists fresh.
- **EPG Data**: XMLTV files contain placeholder program guides (2-hour current window). For real program schedules, users can integrate iptv-org/epg or their app's native EPG source.
- **Data Source**: All stream URLs sourced from [iptv-org/iptv](https://github.com/iptv-org/iptv) (public collection).
- **Legal**: No video files stored here. This repo contains only user-submitted links to publicly available streams. See iptv-org's [Legal](https://github.com/iptv-org/iptv#legal) section for details.

## Troubleshooting

**Streams not loading:**
- Some streams may be geo-restricted or temporarily offline. Wait for the next daily refresh (~24 hours) or manually trigger a workflow run from Actions.
- Verify your IPTV app settings (network, proxy, firewall).

**EPG not showing:**
- Confirm the EPG URL is set correctly (ends with `.xml`).
- Check that channel `tvg-id` values match between playlist and EPG (they should auto-match).

**Update workflow not running:**
- Ensure the GitHub repo is public (required for free GitHub Actions).
- Check the Actions tab for any workflow run logs or errors.

## Custom Updates

To modify the workflow:
1. Edit `.github/workflows/update-playlists.yml` in the repo.
2. Adjust the cron schedule, concurrency, or validation logic.
3. Commit and push; next run will use the updated workflow.

## Contributing

Want to improve categories, add more validation, or customize the workflow? Fork or open an issue.

---

**Last Updated:** Auto-refreshed daily via GitHub Actions  
**Source:** [iptv-org/iptv](https://github.com/iptv-org/iptv)  
**Provider Name for Apps:** Filtered US IPTV
