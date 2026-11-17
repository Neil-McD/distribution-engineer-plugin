---
name: link-placement
description: "Where each tracked link goes (YouTube videos, each profile's bio, one-off places), which tool makes it, and never typing a link. Use it when putting links on videos or profiles, or making a link for an event, email or guest spot."
---

# Place tracked links

Every link to the offer goes through Distribution Engineer, so each visit and sale is credited to the piece of content that
earned it. Read `/products/links` (the links there are) and `/audience/funnel.md` (where content sends people now) first.

## Where each link goes

| Place | Which link | How |
|---|---|---|
| YouTube videos | The funnel link, carrying each video's own tag, first in the description | `put_funnel_link`: propose on one video, let the owner check it on YouTube, then the rest |
| Instagram, X and LinkedIn profiles | Each profile's own bio link | `links` bio: it makes the link once and reuses it. Platforms don't let anyone set a bio for the owner, so write one short bio line per profile in their voice, with that profile's link, for them to paste |
| Posts on Instagram, X, LinkedIn and Shorts | None in the post | The caption points to the bio (LinkedIn: Featured) |
| One-off places: an event, a guest spot, an email, a newsletter, a podcast | A new link for that place | `links` create, named for the place, so its visits are counted apart |
| A link that should stop working | Retire it | `links` retire, by name: its visits and sales stay credited |

## Rules

- Never type, shorten, wrap or edit a link. Use the address a tool returns, exactly.
- One offer: old offers in descriptions compete with it. With `put_funnel_link`, pass the old offers' sites as
  replace_hosts; never social profiles or tools mentioned in a video.
- Before changing what's live, tell the owner exactly what changes and get their yes.
