# First AI Projects

Two small web tools, built while exploring Claude (Anthropic).

## Files

- **`session-ampel-v3.html`** – Multi-provider traffic-light indicator (Claude, ChatGPT, Gemini, Meta AI) for AI usage limits, plus a manual usage score for the current session. Each provider is labeled by evidence quality:
  - **Claude**: based on Anthropic's confirmed peak-hour policy (weekdays 13:00–19:00 GMT, converted automatically to the viewer's local time)
  - **ChatGPT**: labeled *unconfirmed* — no official policy exists, only anecdotal daytime-slowdown reports
  - **Gemini / Meta AI**: labeled *N/A* — no time-of-day peak concept (Gemini uses request/token quotas) or no reliable data found (Meta AI)
- **`session-ampel.html`** – original single-provider (Claude-only) version, kept for reference.
- **`gedankensammler.html`** – Freeform note-taking tool with AI-assisted summary of the underlying thread of thought.

## Usage

All files are plain HTML/CSS/JS with no build step. Just open them in a browser (double-click), or host them via GitHub Pages.

## Note

Learning projects only — no claim to completeness or production readiness. Where a claim isn't officially confirmed, the tool says so explicitly rather than guessing silently.

## Motivation

This tool was built with free-tier AI users in mind — people who come home after an 8-hour shift with limited time to explore AI, only to run into usage limits faster than expected, especially during peak hours. A single evening or day off can end up being just an hour of actual hands-on time once limits kick in. The Session Traffic Light is a small attempt to make that constraint visible upfront, so users can plan around peak hours instead of discovering the limit mid-conversation — turning a frustrating surprise into a manageable, resource-conscious habit.
