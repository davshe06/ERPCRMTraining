# Spring Training — ERP & CRM

A gamified training app that teaches an IT and digital staffing sales team
about ERPs and CRMs, so they can hold consultative conversations with clients
and candidates.

The whole app is one file, `index.html`. There is no build step and no
dependency beyond the Barlow fonts from Google Fonts. Open the file in a
browser to run it, or serve the repository with GitHub Pages
(Settings → Pages → deploy from the `main` branch, root folder).

## What is in it

- **Lessons** — nine "innings", each four short cards and a four-question quiz:
  ERP 101, CRM 101, how they connect, the ERP and CRM platforms, implementation
  projects, upgrades and migrations, roles, and the consultative conversation.
- **Platforms** — sixteen reports (ten ERP, six CRM) with best fit, advantages,
  disadvantages, upgrade paths, words to listen for and the staffing angle.
- **Games** — Which System? (timed ERP-or-CRM sorter), Jargon Match, Go-Live
  Lineup (ordering), Fill the Req (scenario → role) and Client Call (three
  branching conversations scored on a trust meter).
- **Playbook** — discovery questions with copy buttons, trigger events,
  objection responses, a phase-by-role table and a searchable glossary.

XP, ranks (Rookie → MVP) and badges are kept in `localStorage` per browser.
Games pay XP only for beating a personal best.

## Leaderboard

The Leaderboard tab shows everyone who has joined, ranked by XP. A player
joins by entering a display name; from then on their name, XP, innings
finished and badge count are sent to a Supabase table after each change.

- Table `public.erpcrm_leaderboard` in the BookFinder Supabase project. Row
  level security is on with no policies, so the API roles cannot read or
  write it directly.
- The app calls three database functions: `erpcrm_submit`, `erpcrm_board` and
  `erpcrm_remove`. Each browser generates a secret player key that identifies
  its own row; keys are never returned to other players.
- The project URL and publishable key in `index.html` are meant to be public.
- Scores are reported by the browser and only range-checked by the database,
  so a determined person could post a false score. There are no accounts: a
  player who switches browser or clears site data starts a new entry.

## Editing the content

All content sits in the `CONTENT` block at the top of the script in
`index.html`, as plain arrays (`LESSONS`, `PLATFORMS`, `GLOSSARY`, `CALLS`, …).
In every quiz the first option is the correct one; options are shuffled on
screen.

Vendor support dates in the content (SAP ECC 2027, Dynamics GP 2029) were
written from memory and move over time. Check them against the vendor's site
before relying on them.
