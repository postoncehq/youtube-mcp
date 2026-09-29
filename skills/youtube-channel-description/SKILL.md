---
name: youtube-channel-description
description: Write a YouTube channel description (the About text) and channel keywords that tell viewers what the channel is, who it's for and when new videos come out, for the user to paste into YouTube Studio. Use when the user asks for a YouTube channel description, About section, channel bio, channel keywords, or to rewrite their channel description.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# YouTube channel description

Write the channel's About text and keywords. The PostOnce MCP publishes videos; it can't edit channel settings, so the user pastes the result into YouTube Studio themselves.

## Before writing

Get or infer: what the channel covers, who it's for, what makes it different, how often new videos come out (only if true), the person or brand behind it, links to feature, and a contact email for business inquiries if they want one. Read a few of their video titles if they share them. Never invent subscriber counts, credentials or upload schedules.

## Rules

- The first sentence does the work. It shows in search results and the channel preview: say what viewers get and for whom, with the main keyword in plain words. "Weekly tutorials on editing short-form video for small brands."
- Then: what kinds of videos to expect, who's behind the channel, and why to subscribe, in 2–4 short paragraphs.
- Use the words people search for the topic naturally, once or twice. No keyword lists in the text.
- Write in the channel's voice: first person for a creator, "we" for a brand.
- YouTube's limit is 1,000 characters. Most good descriptions use 300–800.
- Links and the business email go in the channel's dedicated link and contact fields, not buried in the text.

## Keywords

Channel keywords (YouTube Studio > Settings > Channel > Basic info > Keywords) help YouTube understand the channel. Give 8–15: the main topic, subtopics, the audience and the channel or brand name. Wrap multi-word keywords in quotes.

## Anti-patterns

"Welcome to my channel!" as the first line, a list of every topic ever covered, promises of a schedule they don't keep, hashtags, and emoji walls.

## Output

Return:
1. The description exactly as it should appear, with its character count against 1,000.
2. A one-line alternative first sentence.
3. The keyword list, ready to paste.

Tell the user where to paste each: YouTube Studio > Customization > Profile (description and links) and Settings > Channel > Basic info (keywords). Offer next steps that the MCP can do: plan uploads with `youtube-content-calendar` or publish a video with the `postonce` skill.
