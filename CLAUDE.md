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

**Current focus (set 2026-07-14): the content production workflow** — making the
pipeline from idea → script → thumbnail → publish → promote → review faster and
more consistent. See "Content production pipeline" below.

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

## Content production pipeline

The workflow, stage by stage, and which tool owns each. Files live in `content/`.

| # | Stage | Tool(s) | Output |
|---|---|---|---|
| 1 | Ideate | (research) | Topic + hook + target level (A1–C2) |
| 2 | Brief/script | `content/briefs/` (from TEMPLATE) | Filled brief + script |
| 3 | Thumbnail/graphics | Canva | Thumbnail, Shorts graphics |
| 4 | Assets/lesson plan | Google Drive | Worksheet, downloadables |
| 5 | Schedule | Google Calendar | Publish date/time slot |
| 6 | Publish | YouTube | Live video |
| 7 | Promote (optional) | Meta Ads (posts) / Google Ads (YouTube video ads) | Campaign |
| 8 | Review | `reports/` (dated) | Snapshot + learnings |

Cadence to sustain: daily **Word of the Day** Short + periodic long-form
podcast + multi-part **Shorts series** (e.g. Dunning–Kruger).

To start a new piece: copy `content/briefs/TEMPLATE-video-brief.md` to a dated,
titled file and fill it in. Track upcoming/published items in
`content/content-calendar.md`.

### Paid promotion notes (as of 2026-07-14)
- Meta Ads account: **AccessorizeR** (`10150978289537110`, USD, business
  *Fluentora-Ads*). A second account (`768098149695958`, PKR) is not MCP-enabled.
- The one active Meta ad is a **boosted engagement post** (Page-visit objective),
  NOT a video ad — no video-view metrics exist for it.
- **YouTube video ads (real YouTube views) require Google Ads**, which is not yet
  connected here. Connect it if promoting videos for views is a goal.

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
