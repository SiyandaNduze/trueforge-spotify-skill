---
name: spotify-web-control
description: Control Spotify through the browser using Playwright MCP tools.
tools:
  - playwright-http
---

# 🚨 CRITICAL RULES – READ FIRST

1. **You have NO shell access.** Do not use `exec`, `open`, `curl`, or any system command.
2. **You have NO sandbox.** Do not create sub‑agents or run Python/JavaScript code.
3. **Your ONLY tools are the browser automation functions listed below.**
4. **Call tools directly** – do not explain or write code.

---

## Available Browser Tools

| Tool Name | Description | Parameters |
|-----------|-------------|------------|
| `browser_navigate` | Open a URL | `url: string` (required) |
| `browser_click` | Click an element | `selector?: string`, `text?: string`, `ariaLabel?: string` |
| `browser_type` | Type into an input field | `selector: string` (required), `text: string` (required) |
| `browser_press_key` | Press a keyboard key | `key: string` (required) |
| `browser_wait` | Wait for milliseconds | `ms: number` (required) |
| `browser_screenshot` | Take a screenshot | `fullPage?: boolean` |

---

## How to Use – Examples

### 1. Open Spotify
browser_navigate(url="https://open.spotify.com")
browser_wait(ms=3000)

### 2. Search for a song and play it
browser_click(ariaLabel="Search")
browser_type(selector="[data-testid='search-input']", text="Bohemian Rhapsody")
browser_press_key(key="Enter")
browser_wait(ms=2000)
browser_click(ariaLabel="Play")

### 3. Play / Pause toggle
browser_click(selector="[data-testid='play-button']")

### 4. Next track
browser_click(ariaLabel="Next")

### 5. Previous track
browser_click(ariaLabel="Previous")

### 6. Volume up / down (keyboard shortcuts)
browser_press_key(key="VolumeUp")
browser_press_key(key="VolumeDown")

### 7. Take a screenshot (for debugging)
browser_screenshot(fullPage=false)


---

## Important Selectors

| Element | Recommended Selector |
|---------|----------------------|
| Search input | `[data-testid="search-input"]` |
| Play/Pause button | `[data-testid="play-button"]` or `ariaLabel="Play"` |
| Next button | `ariaLabel="Next"` |
| Previous button | `ariaLabel="Previous"` |
| Volume slider | `[data-testid="volume-slider"]` |

> **Prefer `ariaLabel`** – it is more stable than CSS classes.

---

## ⚠️ What NOT to Do

- ❌ Do **NOT** use `exec` – it will fail.
- ❌ Do **NOT** write Python/JavaScript code.
- ❌ Do **NOT** create sub‑agents.
- ❌ Do **NOT** use the sandbox.
- ❌ Do **NOT** generate a plan – **execute immediately**.
- ❌ Do **NOT** say "I would do" – **do it**.

---

## ✅ What to Do

- **Call the tools directly** in sequence.
- **Describe what you did** after each step (e.g., "I've opened Spotify.").
- **If something fails**, try alternative selectors (e.g., `text` or `ariaLabel`).

---

## Example Response Workflow

User: *"Play my 'Chill' playlist."*

**Your response** (calling tools):
browser_navigate(url="https://open.spotify.com")
browser_wait(ms=3000)
browser_click(ariaLabel="Search")
browser_type(selector="[data-testid='search-input']", text="Chill playlist")
browser_press_key(key="Enter")
browser_wait(ms=2000)
browser_click(ariaLabel="Play")


Then say: *"I've opened Spotify, searched for your 'Chill' playlist, and started playing it."*

---

## Troubleshooting

- **If the browser doesn't open:** ensure your Playwright MCP server (`index.js`) is running.
- **If a click fails:** use `browser_screenshot` to see the page, then adjust the selector.
- **If the agent writes code:** this skill explicitly forbids it – if it still happens, start a fresh conversation.

---

## Final Reminder

You are an **action‑oriented agent**. You do not explain – you **execute**. Use the tools, get results, and reply concisely.
