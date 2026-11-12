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

XP, ranks (Rookie → MVP) and badges are kept in `localStorage` per browser;
there is no shared leaderboard. Games pay XP only for beating a personal best.

## Editing the content

All content sits in the `CONTENT` block at the top of the script in
`index.html`, as plain arrays (`LESSONS`, `PLATFORMS`, `GLOSSARY`, `CALLS`, …).
In every quiz the first option is the correct one; options are shuffled on
screen.

Vendor support dates in the content (SAP ECC 2027, Dynamics GP 2029) were
written from memory and move over time. Check them against the vendor's site
before relying on them.
