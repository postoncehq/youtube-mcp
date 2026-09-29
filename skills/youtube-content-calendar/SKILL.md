---
name: youtube-content-calendar
description: Plan 1–4 weeks of YouTube videos and Shorts from the user's goals and content pillars, or by repurposing a blog post, video or transcript, draft the title and description for each slot, and schedule them with the PostOnce YouTube MCP once the videos exist. Use when the user asks for a YouTube content calendar, a YouTube upload schedule, YouTube video ideas, or to plan or repurpose content for YouTube.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# YouTube content calendar

Plan a realistic run of uploads, draft each one, and schedule them through PostOnce as the videos get made. Every YouTube post needs a video, so the calendar has two stages: plan and draft now, schedule when each file exists.

## Before planning

Get or infer: the channel's goal (search traffic, subscribers, leads, sales), the audience, 2–4 content pillars, how many long videos and Shorts they can actually produce per week, the timezone, and what's already made. If they give a source (blog URL, long video, transcript, notes), plan from it first. Never invent results, guests or events.

## Building the plan

- Cadence they can keep beats an ambitious one. One long video a week plus a few Shorts is a strong plan for most solo creators.
- Long videos: one searchable topic each. Write the keyword first, then the angle.
- Shorts: cut from the week's long video where possible (self-contained moments), plus a few standalone ideas. Vertical, up to 3 minutes.
- Rotate pillars so no week is all one topic.
- Repurposing: one long video can feed several Shorts, and each Short can go to TikTok, Instagram Reels and Facebook in the same `create_post`.
- Use the user's own best times if they know them; otherwise pick consistent days and times and say it's a starting point.

## Each slot

| Field | Content |
| --- | --- |
| Date and time | With timezone |
| Format | Long video or Short |
| Pillar and keyword | One each |
| Title | Under 60 characters (`youtube-title-generator` rules) |
| Description | First two lines with the keyword, links, 3–5 hashtags (`youtube-description-generator` rules) |
| Privacy | `public` unless the user says `unlisted` or `private` |
| Production note | Script, thumbnail idea, and what footage it needs |

## Scheduling through PostOnce

1. On approval, save slots without a finished video as drafts with `create_draft` (the title on the first line, then the description), so nothing is lost.
2. When a video file is ready (one file, up to 768 MB; MP4, MOV or WebM through `create_upload_url`), upload it and call `create_post` with `publish_at` for that slot, the video in `media`, and `platform_options` `title`, `description`, `privacy` and, if relevant, `categoryId` and `ai_generated`.
3. Call `get_post` to confirm each one is scheduled, and report the list back.

PostOnce uploads the video at the scheduled time; it doesn't use YouTube's own scheduled-publish setting. Scheduled posts can be changed with `update_post` or cancelled with `cancel_post` before they run. Custom thumbnails are uploaded in YouTube Studio after the video is live.

## Output

Return the calendar as a table (one row per slot), then the full title and description for each slot. Ask for approval, then confirm the channel and timezone before creating drafts or scheduled posts with the `postonce` skill.
