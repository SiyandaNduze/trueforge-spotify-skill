# Spotify Web Control Skill

An agent-skill definition for controlling Spotify through browser automation with Playwright-compatible MCP tools.

The skill instructions live in [`SKILL.md`](./SKILL.md). They describe browser actions such as navigating to Spotify, searching for music, play/pause, skipping tracks, changing volume, and capturing screenshots for debugging.

## Requirements

- A compatible agent runtime that supports the skill format used in `SKILL.md`.
- A configured Playwright MCP/browser automation service exposing the browser actions referenced by the skill.
- Access to Spotify in the browser; playback and account features depend on Spotify's current UI and account state.

## Setup

1. Clone this repository:
   ```bash
   git clone https://github.com/SiyandaNduze/trueforge-spotify-skill.git
   cd trueforge-spotify-skill
   ``
2. Review `SKILL.md`.
3. Install or register the skill using the instructions for your agent runtime.
4. Configure the required browser automation tools in that runtime and test against a non-sensitive Spotify session.

This repository contains the skill instructions; it does not include the Playwright MCP server implementation.

## Safety and reliability

- Browser selectors can change when Spotify updates its interface.
- Confirm the active account and intended track or playlist before performing actions.
- Avoid exposing browser sessions, cookies, or account credentials.
- Do not assume playback succeeded until the browser tool confirms the action.

## Repository contents

- `SKILL.md` — skill metadata, browser-tool expectations, examples, and troubleshooting notes.
