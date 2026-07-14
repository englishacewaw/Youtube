# CLAUDE.md — Fluentora YouTube Growth Workspace

This file is auto-loaded by Claude Code at the start of every session. It gives
Claude the context to be useful immediately. Keep it up to date.

## What this project is

This is the operations workspace for the **Fluentora** YouTube channel — an
English-teaching brand (lessons A1–C2, podcasts, and "Word of the Day" shorts).
The goal of the work here is **channel growth**: more views, subscribers, watch
time, and conversions to fluentora.com lesson plans / 1-on-1 bookings.

This repo is not a traditional software codebase. It is a control surface for
content planning, analytics, and marketing automation across the connected
tools below. Deliverables are usually reports, plans, drafts, and data pulls —
not application code.

## The channel (facts)

- **Name:** Fluentora 4 Real Speaking - Real fluency
- **Handle:** [@fluentora4u](https://www.youtube.com/@fluentora4u)
- **Channel ID:** `UCKveFMZrRQc8augvvU0-qWg`
- **Owner/coach:** Umer
- **Website:** https://www.fluentora.com
- **Country:** PL · **Primary language:** English

### Snapshot (update when you pull fresh numbers — do not trust this blindly)
- As of **2026-07-14:** 782 subscribers · 339 videos · 45,852 total views

### Content formats observed
- **Word of the Day** — daily B1 vocabulary quiz Shorts (~15–60s)
- **Podcast episodes** — long-form B1/B2 conversation lessons (20–30 min)
- **Shorts series** — e.g. multi-part explainers (Dunning–Kruger 3-part series)

## Connected tools (via MCP) and what they're for

| Tool | Use it for |
|---|---|
| **YouTube** (Composio) | Channel stats, video lists, per-video metrics, activities |
| **Meta Ads** (META-_MCP) | Paid promotion: campaigns, ad videos, insights, spend/reach/CPV |
| **Canva** | Thumbnails, Shorts graphics, brand designs, exports |
| **Gmail** | Outreach, subscriber/lead email, notifications |
| **Google Calendar** | Content/publishing schedule, reminders |
| **Google Drive** | Lesson plans, scripts, assets, saved reports |
| **GitHub** | This repo (versioning plans, reports, configs) |

### How to reach YouTube data
Prefer Composio tools via `COMPOSIO_MULTI_EXECUTE_TOOL`. Key slugs:
- `YOUTUBE_GET_CHANNEL_STATISTICS` (use `mine: true`)
- `YOUTUBE_LIST_CHANNEL_VIDEOS` (use `mine: true`; videoId is at
  `items[].snippet.resourceId.videoId`, NOT `items[].id`)
- `YOUTUBE_GET_VIDEO_DETAILS_BATCH` (≤50 IDs; stat values are strings)

> Note: The YouTube **Data API does not report paid-promotion/ad metrics**.
> "Promoted video" performance (spend, impressions, CPV, CTR) comes from
> **Meta Ads** or Google Ads, not from YouTube. Clarify the platform before
> reporting "promoted" numbers.

## Conventions

- Save data pulls and analyses to `reports/` as dated Markdown
  (e.g. `reports/2026-07-14-channel-snapshot.md`) so trends are trackable.
- Always **date** any stats you record — YouTube numbers change constantly.
- Reference videos by title **and** ID/URL so links stay clickable.

## Guardrails (ask before doing)

- **Never** publish, post, comment, or send email/ads on the user's behalf
  without explicit confirmation — these are public/outward-facing actions.
- **Never** spend ad budget or create/modify Meta Ads campaigns without
  explicit sign-off on the amount and audience.
- Reading/analytics is fine to do proactively; writing/sending is not.

## Working branch

Development happens on `claude/youtube-promoted-video-setup-noxac5`.
Commit plans/reports with clear messages; push when a piece of work is done.
