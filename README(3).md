# First AI Projects

Two small web tools, built while exploring Claude (Anthropic).

## Files

- **`session-ampel-v4.html`** – Multi-provider traffic-light indicator (Claude, ChatGPT, Gemini, Meta AI) for AI usage limits, plus a manual usage score for the current session. Each provider is labeled by evidence quality:
  - **Claude**: **CONFIRMED** — the only provider with an actual time-of-day rule (weekdays 13:00–19:00 GMT, converted automatically to the viewer's local time)
  - **ChatGPT, Gemini, Meta AI**: **CONFIRMED (DIFFERENT MODEL)** — all three have real, officially confirmed capacity measures, just none of them tied to time of day (model fallback / sign-up pauses for ChatGPT, prompt complexity for Gemini, plan tier for Meta AI)
- **`session-ampel-v3.html`** / **`session-ampel.html`** – earlier versions, kept for reference (see changelog below).
- **`gedankensammler.html`** – Freeform note-taking tool with AI-assisted summary of the underlying thread of thought.

## What changed in v4

- Added ChatGPT, Gemini, and Meta AI as selectable tabs alongside Claude.
- Corrected an early assumption that all four providers throttle by time of day — verified against real sources instead, and only Claude actually does.
- Added a **"Your key lever"** box per provider showing what actually drains your usage there (time of day for Claude; model/tier for ChatGPT; prompt complexity/features for Gemini; plan tier for Meta AI).
- The manual usage-score buttons now match each provider's real cost driver (e.g. "Media generation / Deep Research" for Gemini) instead of a one-size-fits-all "short vs. long reply".
- Source details are now collapsed by default behind a "Show source & details" link, so the interface stays clean while remaining fully transparent on request.

## A note on the manual counter — and why it's manual

The usage-score counter has no automatic way to know what you actually did in your AI chat — that's a deliberate privacy choice, not a missing feature. Reading your conversations automatically would mean the tool (or a browser extension doing it for you) needs access to the content of your chats, which is exactly the kind of access you should be careful about handing to a third-party tool.

If you'd rather not click the buttons yourself, some browser extensions and userscripts exist that claim to track AI usage automatically (for example by reading page content or intercepting network requests). Before using one, be aware of the trade-offs:

- It needs broad permission to read the pages you're on, which for an AI chat means it can technically see everything you type and everything the AI replies — including anything sensitive or personal.
- Unofficial extensions are not reviewed by Anthropic, OpenAI, Google, or Meta, and their code quality, maintenance, and data-handling practices vary widely and can change without notice.
- Some may send data to a third-party server for "analytics," which defeats the point of a private local counter.

If you do go looking for one, prefer options that are open-source (so the code can actually be inspected) and that clearly state they work entirely locally, with no external server involved. This project intentionally stays manual and local (plain `localStorage`, nothing sent anywhere) so there's nothing to trust beyond the code in this file.

## Usage

All files are plain HTML/CSS/JS with no build step. Just open them in a browser (double-click), or host them via GitHub Pages.

## Note

Learning projects only — no claim to completeness or production readiness. Where a claim isn't officially confirmed, the tool says so explicitly rather than guessing silently.

## Motivation

This tool was built with free-tier AI users in mind — people who come home after an 8-hour shift with limited time to explore AI, only to run into usage limits faster than expected, especially during peak hours. A single evening or day off can end up being just an hour of actual hands-on time once limits kick in. The Session Traffic Light is a small attempt to make that constraint visible upfront, so users can plan around peak hours instead of discovering the limit mid-conversation — turning a frustrating surprise into a manageable, resource-conscious habit.
