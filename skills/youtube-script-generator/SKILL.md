---
name: youtube-script-generator
description: Write long-form YouTube video scripts with a hook for the first 30 seconds, retention beats, pattern interrupts, a payoff and a call to action, plus the title and description to publish it with the PostOnce YouTube MCP. Use when the user asks for a YouTube script, a script generator, a video outline, or to turn an article, notes or idea into a YouTube video script.
metadata:
  author: PostOnce
  version: "0.1.0"
---

# YouTube script generator

Write one script for one long-form video (roughly 5–20 minutes). For vertical videos up to 3 minutes, use the `youtube-shorts-script` skill instead.

## Before writing

Get or infer: the topic and the one promise the video makes, the viewer (beginner or experienced), target length, the presenter's voice (read a past script or transcript if offered), what's on screen (talking head, screen recording, B-roll), and the action the viewer should take at the end. If the user gives a source (article, notes, transcript), keep its facts and cut the rest. Never invent data, quotes, case studies or personal stories.

## Structure

| Section | Job | Length |
| --- | --- | --- |
| Hook | Deliver on the title and thumbnail in the first line. Show the result, the stakes or the problem. | 0:00–0:30 |
| Setup | Why this matters to the viewer and what they'll have by the end. No channel intro, no "before we start, subscribe". | 30–60 seconds |
| Body | 3–7 beats in a clear order (steps, mistakes, levels). Each beat: point, proof or example, what to do. | Most of the video |
| Payoff | The result, summarized in one or two lines. | Short |
| CTA | One ask tied to the video: a related video, a free resource or a subscribe with a reason. | 1–2 sentences |

## Keeping people watching

- Open loops: tease a later beat early ("the third setting is the one most people miss") and pay it off.
- Re-hook between beats with a one-line transition that says what's next and why it matters.
- Pattern interrupts every 30–60 seconds: a cut to screen, a B-roll note, an on-screen text callout, a quick example. Mark them in the script.
- Show, don't narrate: when something is on screen, the script should say less.
- Write for the ear: short sentences, contractions, one idea per sentence. Read it aloud.

## Anti-patterns

Long intros, "Hey guys, welcome back", asking for likes before delivering value, filler recaps, and ending with "that's it for today" and no next step.

## Output

Return:
1. The script with section headings, spoken lines, and `[ON SCREEN: …]` / `[B-ROLL: …]` notes, plus a rough runtime.
2. Three title options (use `youtube-title-generator` rules) and a thumbnail idea that pairs with the best one.
3. Offer a description with chapters from the final timestamps (`youtube-description-generator`).

Once the video is recorded and exported (one file, up to 768 MB), offer to upload and publish or schedule it with the `postonce` skill, setting `platform_options.title`, `description` and `privacy`. Confirm the channel, privacy and time before calling `create_post`.
