---
name: youtube-shorts-script
description: Write YouTube Shorts scripts for vertical videos up to 3 minutes, with a hook in the first second, a loopable ending, and the Short's title and description, ready to publish with the PostOnce YouTube MCP. Use when the user asks for a Shorts script, YouTube Shorts ideas, a script for a vertical video, or to cut a long video or article into Shorts.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# YouTube Shorts script

Write one script per Short. If the user wants several (for example from one long video), write each as its own Short with its own hook.

## Before writing

Get or infer: the one idea, who it's for, the format (talking head, screen recording, voiceover on B-roll, text on screen), target length, and any source to cut from. From a long video or transcript, pick self-contained moments that make sense with no context. Never invent facts, results or stories.

## Format facts

- Shorts are vertical (9:16, 1080×1920 works) and up to 3 minutes. Most land best well under a minute; only go longer when the content earns it.
- PostOnce treats portrait videos as Shorts; YouTube classifies the final format from the video itself. `#shorts` is optional.
- One video per post, up to 768 MB, MP4, MOV or WebM.

## Structure

| Beat | Job | Time |
| --- | --- | --- |
| Hook | Say or show the payoff, the problem or a surprising line in the first second. The first frame must work with the sound off. | 0–2 s |
| Body | One idea delivered fast: steps, a before/after, one example. Cut every word that doesn't move it forward. | Most of it |
| End | Land the point, then end on a line or image that flows back into the start so it loops. | Last 1–3 s |

Rules:
- Start mid-action. No intro, no "in this video".
- On-screen text for the key line of every beat, inside the middle of the frame: the top and bottom are covered by the Shorts UI.
- A visual change every few seconds: cut, zoom, new text, new angle.
- No CTA that pauses the video. If there's an ask, make it one short line at the end, or point to the related long video.

## Title and description

- Title: short and plain, 3–6 words naming the moment or result, under 60 characters. Pass it as `platform_options.title`; otherwise the first line of the content is used.
- Description: one or two lines on what it's about, then 2–3 single-word hashtags. PostOnce sends up to 8 description hashtags as tags.

## Output

Return, per Short: the hook line, the script with `[ON SCREEN: …]` and `[SHOT: …]` notes, the estimated length, the title and the description.

Once the vertical video is exported, offer to upload and publish or schedule it with the `postonce` skill. The same file can go to TikTok, Instagram Reels and Facebook as extra targets in one `create_post`, with a `content_override` per platform. Confirm the channel, privacy and time before calling `create_post`.
