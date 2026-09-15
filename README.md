# Thought Leadership Workflow

An editable AI skill for turning real work and expertise into LinkedIn posts and long-form articles.

It learns your context on first use, checks your source material and past content, then helps you plan, draft, and revise. It does not publish for you.

## What you get

- Guided first-use setup for your audience, experience, voice, topics, and goals.
- A local author profile you can edit at any time.
- Content planning based on your work and evidence.
- Checks for repeated arguments, unsupported claims, and repetitive post structures.
- LinkedIn posts, article repurposing, and long-form drafts.
- A review log that distinguishes drafts from published work.

No company positioning, paid tool, API key, analytics account, or scraping service is required. Source files and writing samples can be supplied directly.

## Install

This repository contains a standard Markdown skill folder:

`skills/thought-leadership-workflow/`

Copy that whole folder into your AI assistant's supported skills directory. Keep its references, templates, and agents folders together. Installation paths depend on the assistant. Use its current installation instructions rather than copying the entire repository into a skills folder.

If your assistant does not load skills, give it SKILL.md and the linked references as instructions. This is a manual workflow, not an installed integration.

## First use

Ask your assistant:

> Use $thought-leadership-workflow to set up my content profile.

Installing the folder alone does not run setup. The first invocation starts a short conversation. Setup is driven by the assistant, not an executable installer or form service.

You will cover identity, audience, subject knowledge, goals, source material, voice, available formats, and review preferences. The assistant asks in small groups. You can say “skip” or “use a provisional default” for optional fields. It shows your profile for confirmation before using it as the baseline.

With filesystem access, private working files go in `.content-workspace/` in a project you choose, outside the installed skill. Without it, the assistant returns the profile as Markdown for you to save and reuse.

## Use it

- “Plan next week's posts from these project notes.”
- “Turn this article into three distinct LinkedIn posts.”
- “Draft a post about this decision and keep my contribution accurate.”
- “Revise this draft using my edits.”
- “Update my content profile. My audience has changed.”

Past content and analytics improve the work but are optional. No history means no verified repetition audit. No performance data means no performance claim.

## Edit it

Edit `profile.md` for your context, voice, and preferences. Edit the skill and templates to change the workflow. Topics, cadence, post length, questions, humor, hashtags, visuals, and CTAs are configurable. There is no compulsory hook or three-point formula.

Your context is private working material. Share the clean skill folder, not your filled profile, draft folder, transcripts, or analytics exports. The included `.gitignore` helps when working inside this repository; it is not a privacy scanner and does not protect files already tracked by Git.

## Limits

A skill guides an assistant. It cannot guarantee perfect source checking, privacy, voice matching, or compliance with every instruction. Review the output. It does not install connectors, scrape profiles, create reminders, schedule posts, or publish content.

## License

MIT. You may use, edit, and redistribute this package under the included license.
