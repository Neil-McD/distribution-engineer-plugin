---
name: using-distribution-engineer-tools
description: "When and how to use each tool on the owner's behalf: the preview, then the owner's yes, then confirm with the code; and each tool's own rules. Use it before using any tool that changes something."
---

# Using Distribution Engineer's tools

How to use each tool well, on the owner's behalf. The tools' own descriptions say what each one does; this says when and how.
Some tools come with the Setter and CRIS plans: a tool you aren't offered isn't on this workspace's plan.

## The rule for every change

A tool that changes something outside Distribution Engineer (a post, a video's description, a link, a message, a
setting) changes nothing on its first call. It returns exactly what would change, and a code.

A few actions change nothing anyone else can see and act on their first call, with no preview: making a new tracked link
or a profile's bio link (`links` `create` and `bio`), and saving a draft of the form (`offer` `save_form`). Before one of
those, tell the owner what you are about to make.

1. Show the owner that preview, word for word: its own words, never your summary of it.
2. Wait for the owner's yes, in this conversation, for exactly that.
3. Make the same call again with `confirm` set to the code.

If they want anything different, make the changed call without the code, and show the new preview. Never confirm on your
own judgment, from an earlier yes to something else, or because a task seems to call for it. If a call is refused, tell the
owner why, in the tool's words.

## Posting

- **`prepare_post`:** `action: inspect` first, to see the accounts, the time now, and for YouTube the post's own tracked link;
  then `action: prepare` with the caption.
  - Put the tracked link on a YouTube description's first line, exactly as given.
  - Leave the link out (`no_cta`) only when the owner asked for no link, and tell them.
  - An image Instagram would crop is refused by name: ask the owner what to do.
  - A long-form video's title and thumbnail: see `youtube-video-package`.
  - Captions: see `post-captions`.
- **`schedule_post`:** only when the owner asks to schedule, for a post they've seen prepared. Pick a time only when they ask
  you to choose.
- **`edit_post`:** only when the owner asks. A new caption follows the same rules as preparing, and is shown to them first.
  A clip swapped in (`replace_with`) is prepared with `prepare_post` and shown first.
- **`schedule_cancel_publish_job`:** only for the entry the owner names.

## YouTube

- **`youtube_descriptions`:** only when the owner asks or agrees.
  - Write each draft with `youtube-descriptions`, from the video's transcript; read it with `start_ms` and `end_ms` for the
    times chapters need.
  - Start with `scope: first` (one video), so they can check it on YouTube, then `scope: rest`.
  - Use `replace_hosts` only for addresses the owner said to remove.
  - Never write a link, a hashtag or a whole description yourself.
  - `youtube_descriptions_status` shows progress.
- **`put_funnel_link`:** only when the owner asks or agrees.
  - Read `/audience/funnel.md` first, and judge which addresses in descriptions are old offers competing with the one the
    workspace sells. Pass those as `replace_hosts`, never social profiles, tools a video mentions, or the funnel itself.
  - Describe the change only in the preview's own words.
  - `scope: first`, then `scope: rest`, as above. `put_funnel_link_status` shows progress.

## Links and the offer

- **`links`:** read `/products/links` first.
  - `bio` returns each profile's own link: write one short bio line per profile, in the owner's voice, for them to paste.
  - `create` a link for each new place (an event, a guest spot, an email).
  - See `link-placement`.
- **`offer`:** only on the owner's word. Read `/products/index.md` and its files first.
  - For the form, read `/products/<key>/application.md` and `bookings.md` first. Save the whole form, changed
    (`save_form`), then `publish_form` once they've seen it.
  - `facts`: give only the lists that change, each whole.

## People

- **`person_notes`:**
  - `owner_note` saves the owner's exact words.
  - `improve` writes a reading of the person's own data, citing it. Never record a guess as fact.
  - Plans for later ("follow up in May") are the setter's follow-ups, not notes.
- **`instagram_reply`:** reply to an existing Instagram conversation with the owner’s exact approved words. Show the full preview, then use its confirmation only after the owner agrees. Changed words or a new inbound require a fresh preview. Retry the same approved reply to check delivery; do not work around an uncertain send. This starts no DE agent.
- **`setter`:** only when the owner asks, never on your own judgment.
  - Show them the full message before `send_draft`.
  - `hand_back` lets the setter message that person again.
- **`people_lists`:** name the list and the count to the owner, never ids.
- **`payment_matches`:** `payment_matches_list` shows the open cases. Tell the owner each case in its own words (why), never
  its id, and resolve it only with their answer.
- **`call_attendance`:** `mark` only from the owner's own word ("Sam no-showed"), never from a guess. `call_attendance_read`
  shows what's recorded.
- **`campaigns`:** `campaigns_list` and `campaigns_queue` show where things stand. Start a campaign, set a rule or turn a
  follow-up on or off only on the owner's word. Outcomes are in `/audience/outreach.md`.

## Content and the profile

- **`import_tella_recording`:** only when the owner asks for that recording, to edit it. To read or compare what was said,
  read `/tella` instead. Say it's importing; it's ready when `/tella/index.md` says so.
- **`update_workspace_context`:** give the whole area as it should read, with every still-useful fact from the current one;
  never only the change.
- **`request_strategy`:** include the owner's feedback faithfully. The strategy is done only when it appears under
  `/strategy`.
