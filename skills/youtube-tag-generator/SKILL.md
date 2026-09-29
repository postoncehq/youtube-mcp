---
name: youtube-tag-generator
description: Generate YouTube tags within the 500-character limit, delivered as hashtags for the description (which PostOnce sends as the video's tags) plus a full tag list to paste into YouTube Studio. Use when the user asks for a YouTube tag generator, YouTube tags, keywords for a video, or hashtags for a YouTube video or Short.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# YouTube tag generator

Build one tag set for one video. Tags are a small signal on YouTube: they mostly help with misspellings and closely related searches. The title, description and thumbnail matter more, so keep tags accurate and short rather than long and hopeful.

## How tags reach YouTube through PostOnce

The MCP has no separate tags field. PostOnce takes up to 8 hashtags from the video's description and sends them as its tags (plus a generic `video` tag). So this skill delivers two things:

1. **Hashtags to include** in the description: 3–8 single-word hashtags. These become the uploaded tags.
2. **A full tag list** the user can paste into the Tags box in YouTube Studio (Details > Show more > Tags) after upload, for multi-word tags and anything beyond 8.

## Before writing

Get or infer: the title, the main search keyword, what the video covers, the audience, and the channel or brand name. Read the description or transcript if there is one.

## Building the full list

Order matters; put the most important tags first.

1. The exact main keyword ("repurpose video content").
2. 2–4 close variations and longer phrases people search ("how to repurpose videos", "repurpose youtube videos to tiktok").
3. 2–4 broader topic tags ("content repurposing", "video marketing").
4. Common misspellings or alternate names, only if real.
5. The channel or brand name.

Budget: YouTube allows 500 characters for all tags combined. Commas count, and a tag with spaces counts its surrounding quotes, so count the list as YouTube will. Stop well before 500; 10–20 relevant tags is plenty.

## Hashtags for the description

- Letters, numbers and underscores only: `#contentrepurposing`, not `#content-repurposing` or `#content repurposing`. Anything after a hyphen or space is dropped.
- YouTube shows the first three hashtags above the title, so put the best three first.
- Never use more than 15 hashtags on a video; YouTube then ignores all of them. For Shorts, `#shorts` is optional; YouTube classifies Shorts from the video itself.

## Anti-patterns

Tags for other creators' names or unrelated trending topics (YouTube treats misleading metadata as spam), repeating the same word in 20 forms, and single generic tags like "video" or "funny".

## Output

Return:
- **Hashtags to include:** one line, 3–8 hashtags, best three first.
- **YouTube Studio tags:** one comma-separated line, then its character count against 500.

Offer to add the hashtags to the end of the description and publish or schedule with the `postonce` skill (confirm the channel, privacy and time before `create_post`). The full tag list is for the user to paste into YouTube Studio; the MCP can't edit a video after upload.
