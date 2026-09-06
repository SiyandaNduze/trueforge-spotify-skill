---
name: spotify-web-control
description: Control Spotify through the web browser using Playwright automation
tools:
  - playwright-http
---

# Spotify Web Control Skill

You have access to browser automation tools (`browser_*`). Use them to control Spotify through the web interface at `open.spotify.com`.

## How to Use

1. **Navigate to Spotify**: `browser_navigate(url="https://open.spotify.com")`
2. **Wait for load**: `browser_wait(ms=3000)`

## Common Actions

### Search and Play
- Click search: `browser_click(ariaLabel="Search")`
- Type query: `browser_type(selector="[data-testid='search-input']", text="<song/playlist>")`
- Press Enter: `browser_press_key(key="Enter")`
- Play: `browser_click(ariaLabel="Play")`

### Playback Controls
- Play/Pause: `browser_click(selector="[data-testid='play-button']")`
- Next: `browser_click(ariaLabel="Next")`
- Previous: `browser_click(ariaLabel="Previous")`

### Volume
- `browser_press_key(key="VolumeUp")` or `browser_press_key(key="VolumeDown")`

Always confirm what you've done (e.g., "I've opened Spotify and started playing your playlist.").