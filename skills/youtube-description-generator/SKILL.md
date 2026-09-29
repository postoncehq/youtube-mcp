---
name: youtube-description-generator
description: Write YouTube video descriptions with the keyword in the first two lines, chapters (timestamps) from a transcript, links and hashtags, within 5,000 characters, ready to publish with the PostOnce YouTube MCP. Use when the user asks for a YouTube description generator, a video description, YouTube chapters or timestamps, or to turn a transcript or script into a description.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# YouTube description generator

Write one description for one video, then hand it to the `postonce` skill as `platform_options.description` if the user wants to publish or schedule.

## Before writing

Get or infer: the video's title and search keyword, what it covers, the audience, the links to include (product, resources, socials, a related video), and a transcript with timestamps if the user wants chapters. Never invent links, sponsors, results or timestamps.

## Structure

1. **First two lines (about 150 characters).** They show in search and above "...more". State what the viewer gets and use the keyword naturally in the first sentence. No "In this video I will...".
2. **Summary.** 2–4 short paragraphs in plain language. Work in related terms people search, once each. No keyword stuffing.
3. **Links.** One per line with a label: "Free template: https://…". Put the most important link near the top if the video's goal is a click. Use clean URLs without `&` query strings: PostOnce turns `&` into "and", which breaks the link.
4. **Chapters.** See below.
5. **Hashtags.** 3–5 at the very end. See below.

Hard limit: 5,000 characters. Longer text gets cut off or rejected, so count before you hand it over.

## Chapters from a transcript

- Build chapters only from real timestamps in the transcript or from the user. If the transcript has no timestamps, ask for them or skip chapters.
- The first chapter must be `00:00`. Use at least three chapters, each at least 10 seconds long, in ascending order. YouTube ignores the list otherwise.
- Format: `00:00 Intro`, `02:15 Setting up the account`, one per line. Labels are short and specific; use the keyword in one or two where it fits.
- Use `1:02:30` style for videos over an hour.

## Hashtags and tags

- YouTube shows the first three hashtags above the title. Put the most relevant three first.
- PostOnce sends up to 8 hashtags from the description as the video's tags, so choose them on purpose. Use letters, numbers and underscores only (`#videoediting`, not `#video-editing`); anything after a hyphen or space is dropped.
- YouTube ignores every hashtag on a video that has more than 15. Stay at 3–5 here; use the `youtube-tag-generator` skill for a fuller tag set.

## Anti-patterns

Walls of text, a pasted transcript, repeated keywords, unrelated trending hashtags, links with no label, and `&`, `<` or `>` (PostOnce replaces them because YouTube rejects them).

## Output

Return the description exactly as it will appear, then a line with its character count. Offer to publish or schedule with the `postonce` skill: pass it as `platform_options.description` and the title as `platform_options.title` on the YouTube target. Without `description`, YouTube gets the whole post content, so set both. Confirm the channel, privacy and time before calling `create_post`.
