---
name: youtube-video-package
description: "A long-form video from upload to schedule: its own tracked link, the title, the description (link first, summary, chapters last) and the thumbnail, checked against YouTube's rules. Use it when posting a new long-form YouTube video."
---

# Post a long-form YouTube video

You package one long-form video: its title, description and thumbnail. Distribution Engineer gives it its own tracked
link, checks YouTube's rules and schedules it on the owner's yes. A click on that link, and anything the person goes on
to book or buy, is credited to this video.

## The steps

1. **Bring the video in.** Use `upload_start` and `upload_finish`. If you can't send a file's bytes, ask the owner to add
   it in Assets. Wait until it's ready: it's checked and transcribed first.
2. **Bring the thumbnail in, if the owner has one.** It must be a 16:9 JPEG or PNG under 2 MB; 1280×720 or larger looks best. Use
   `upload_image` for one under 3 MB, otherwise `upload_start`. Never make one up.
3. **Read the transcript.** Read `/assets/transcript.md` with the video's exact title. Everything you write comes from it.
4. **Get the video's link.** Call `prepare_post` with `action: inspect`, `platform: youtube` and the video's exact title.
   It returns `tracking_url`: this video's own link. Never type, shorten or change a link.
5. **Write the title and description** (below).
6. **Prepare.** Call `prepare_post` with `action: prepare`, passing the `caption` (the whole description), the `title`,
   the `thumbnail` (the image's exact title) and a `proposed_time` with timezone. A refusal says what to fix; fix that line
   and prepare again.
7. **Schedule on the owner's yes.** Call `schedule_post`. It schedules nothing yet: it returns exactly what will go out,
   and when, with a code. Show the owner that, and on their yes make the same call again with `confirm` set to the code.

## The title

- **Under 70 characters,** so it isn't cut off. YouTube's limit is 100.
- **The promise, in the words someone would search,** taken from what the video actually delivers.
- **No clickbait** the video doesn't pay off, no ALL CAPS, at most one emoji (and only if the owner uses them).
- **If the owner gave a title, use it as it is.**

## The description, top to bottom

1. **The link line.** `tracking_url` on the first line, with a few words in front of it: what clicking gets them, in the
   owner's words (for example `Book a call: <tracking_url>`). If you leave it out, it's added there anyway.
2. **The summary:** 2–3 sentences, written by the `youtube-descriptions` guide.
3. **Anything the owner asked to include:** credits or disclosures, word for word.
4. **The chapters, last.** Follow the rules in the `youtube-descriptions` guide, taking each time from the transcript's
   timings. Nothing may come after them.

Never add another link, hashtags, a socials block or "subscribe". At most 5,000 characters in all.
