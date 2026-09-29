---
name: youtube-title-generator
description: Write YouTube video titles that rank for the search keyword and earn the click, then set the chosen one when publishing with the PostOnce YouTube MCP. Use when the user asks for a YouTube title generator, title ideas, a better title for a video, or to title a video from a script, transcript or topic.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# YouTube title generator

Write 10 title options for one video, recommend one, and hand it to the `postonce` skill as `platform_options.title` if the user wants to publish or schedule.

## Before writing

Get or infer: what the video actually delivers (read the script, transcript or outline if there is one), who it's for, the search keyword people would type to find it, and whether it's long-form or a Short. Never promise something the video doesn't deliver, and never invent numbers or results for the title.

## Rules

- Put the keyword near the front, in the words people search, not your internal name for it.
- Aim for under 60 characters so the title isn't cut off in search and suggested videos. YouTube's hard limit is 100.
- Make one clear promise: the result, the method or the mistake. One title, one idea.
- Titles and thumbnails work as a pair. The title should add to the thumbnail text, not repeat it.
- Use numbers only when they're true and specific ("7 settings", "in 10 minutes").
- Avoid `&`, `<` and `>`. PostOnce replaces `&` with "and" and angle brackets with look-alike characters because YouTube rejects them in titles.
- No ALL CAPS titles, no clickbait the video doesn't pay off, no stacked emojis, no hashtags in the title.

## Patterns

| Pattern | Template |
| --- | --- |
| How-to | "How to [result] ([qualifier])" · "How to [result] Without [pain]" |
| Keyword + promise | "[Keyword]: [specific outcome] in [time]" |
| List | "[N] [Keyword] [Mistakes / Tips / Tools] for [audience]" |
| Mistake | "Stop [common action] (Do This Instead)" |
| Comparison | "[A] vs [B]: Which [Keyword] Is Better for [use]?" |
| Proof | "I [did the thing] for [time]. Here's What Happened" (only if they did) |
| Shorts | Short and plain; name the moment or result in 3–6 words. |

## Output

Return a numbered list of 10 titles with the character count for each, grouped by pattern. Mark your pick and say why in one line (keyword position, promise, length).

When the user picks one, offer to publish or schedule with the `postonce` skill: pass it as `platform_options.title` on the YouTube target. If no title is set, YouTube gets the first line of the post content, so set it explicitly. Confirm the channel, privacy and time before calling `create_post`.
