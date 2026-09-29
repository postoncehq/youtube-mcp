---
name: youtube-thumbnail-maker
description: Design YouTube thumbnail concepts and render a 1280×720 image (HTML to PNG) ready to upload in YouTube Studio. Use when the user asks for a YouTube thumbnail maker, thumbnail ideas, a thumbnail for a video, or to make or improve a YouTube thumbnail.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# YouTube thumbnail maker

Plan three thumbnail concepts for one video, render the chosen one, and hand the file to the user.

**Upload it yourself in YouTube Studio.** The PostOnce MCP does not set custom YouTube thumbnails. After the video is up, open it in YouTube Studio > Content > Details > Thumbnail > Upload file. YouTube only allows custom thumbnails on channels with intermediate features turned on (phone verification).

## Before designing

Get or infer: the video title (the thumbnail must pair with it, not repeat it), the one promise of the video, the channel's colors and fonts, and any assets: a face photo with an expression, a product shot, a screenshot, a before/after. Never fake a result, screenshot or number the video doesn't show.

## Specs

- 1280×720 pixels, 16:9. Minimum width 640.
- JPEG or PNG, 2 MB or less. Export PNG, and convert to JPEG if it's over 2 MB.
- Keep text and faces out of the bottom-right corner: the video length covers it.

## What makes a thumbnail work

- One focal point: a face with a clear emotion, one object, or one contrast. Readable at phone size in suggested videos.
- 0–4 words of text, large and bold, adding what the title doesn't say. Never the full title.
- High contrast between subject and background; a clean, simple background.
- Show the stakes or the result: before/after, the finished thing, the mistake circled.
- Same style across a channel so viewers recognize it, but each thumbnail distinct.
- For Shorts, YouTube mostly uses a frame from the video; design the first frame instead.

## Concepts

Return three concepts, each with: the idea in one line, the layout (subject position, text position), the exact text (0–4 words), colors, and which assets it needs.

## Rendering

If the environment can render HTML to PNG (for example headless Chrome or Playwright), build the chosen concept as a fixed-size HTML page:

- `<body>` exactly 1280×720, `margin: 0`, `overflow: hidden`, one root element at that size.
- Local or inline assets and fonts only, so the render is deterministic.
- Screenshot at 1280×720 (device scale factor 1) to PNG, check the file size, and look at a small preview (about 320×180) to confirm it still reads.

Otherwise hand the user the layout, text, colors and asset list for Canva, Figma or Photoshop.

## Output

Give the three concepts, mark the pick, and deliver the rendered PNG path (or the design brief). Remind the user to upload it in YouTube Studio once the video is live. Offer to publish or schedule the video itself with the `postonce` skill, and to write the title with `youtube-title-generator` so the pair works together. Confirm the channel, privacy and time before calling `create_post`.
