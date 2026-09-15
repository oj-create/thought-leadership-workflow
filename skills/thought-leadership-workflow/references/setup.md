# First-use setup

On first invocation, start by explaining that setup creates an editable content profile. It does not publish or connect accounts.

Use answers already given in the current conversation. Ask the remaining items in short groups, normally two or three related questions per turn. Wait for answers before the next group. Offer a single fill-in template if the user prefers one form. Do not dump every question at once by default.

Once identity, audience, subject scope, goal, and one usable source are known, offer to confirm a basic profile now or continue with the optional detail. A clear request should not require all four groups. Mark unanswered preferences as unspecified, not guessed. A user who wants detailed setup can complete all groups.

At the save step, offer a project folder chosen by the user or conversation-only use. Do not require a filesystem path to complete setup.

## 1. Author, audience, and purpose

Establish:
- Who the content is for: the user or another named author; role and relevant experience.
- Who should read it, their situation, and what they should learn or do.
- The goal: education, professional reputation, opportunities, business conversations, or another goal.
- Main channel and language.

Do not require a company or product. Company context is optional and is not a reason to turn every post into promotion.

## 2. Expertise and evidence

Ask for the work, decisions, experiments, or subjects they can discuss with firsthand knowledge. Request one usable source for the first draft: notes, a project description, an article, or a supplied example.

Record optional company context only if relevant: plain product explanation, audience, verified capabilities, and claims to avoid. Record what the author did personally versus what others contributed.

Ask which material is public, private but usable in anonymized form, or excluded. Default unclear material to private working context. A request to draft from supplied notes authorizes creating the requested private draft; it is not permission to publish or share those notes elsewhere. Do not block ordinary drafting merely because a public/private label is absent. Omit or anonymize sensitive details, and ask only when the unresolved disclosure choice changes the draft materially. Do not request credentials, private contact lists, or access tokens.

## 3. Voice

Request two or three authored writing samples if available, with comments about what feels right or wrong. A reference writer can help explain preferences but does not establish the author's own voice.

Capture tone, depth, preferred phrasing, formatting, humor, punctuation, questions, hashtags, CTA preferences, and things to avoid. Explain the learning mode: explicit ongoing preferences are saved automatically by default; inferred patterns are proposed for review. Offer review-only or off if preferred. Include the selected mode in the profile confirmation. Ask only about choices not already evident. Accept no samples and mark the voice provisional.

## 4. Cadence and production

Establish a realistic posts-per-week preference, channels, available formats, and review process. Ask about existing published posts or a content log and optional analytics. Allow “no history yet.”

Ask for source locations the assistant may use. Local files are sufficient. Do not assume tools, subscriptions, or access. Record a history review window if useful; propose eight weeks as a configurable starting point, not a requirement to obtain missing history.

## Confirm and save

Summarize the profile, known facts, missing optional evidence, and provisional defaults in a compact review. Ask the user to confirm or correct it.

Until confirmation, mark setup `in_progress`. Do not quietly treat silence as confirmation. If they explicitly ask to skip setup and draft, use supplied facts, mark the draft provisional, and leave setup incomplete.

After explicit confirmation, save `.content-workspace/profile.md` in the chosen working directory with `setup_status: confirmed`. If saving is unavailable or the user chooses conversation-only use, return the completed Markdown profile and explain that it must be supplied again in a future session.

Never put filled profiles, private examples, or source excerpts in the installed skill directory. On later runs, ask only for missing task-specific information or changed context.
