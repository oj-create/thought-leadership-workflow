# Feedback learning

This loop runs when an assistant uses the skill and receives corrections. It does not run in the background or retrain a model. Persistent learning requires readable, writable local working files. Keep it separate from the distributable package.

## Modes and precedence

Read `learning_mode` from the current author's profile:
- `explicit` (default): save unambiguous ongoing writing preferences without another confirmation.
- `review`: propose all durable changes; save only after confirmation.
- `off`: revise the current draft but do not collect observations or change preferences.

A direct request to save, remove, undo, or change the mode is an authorized control action even in off mode. An existing opt-out overrides the default for old profiles. If mode is missing, announce the explicit default at the first eligible correction, not on every run.

Current task instructions outrank saved preferences. A task-specific exception applies only to that draft. A clear new ongoing correction supersedes an older conflicting rule within the same scope. Preserve unrelated profile values and rules. If scope is ambiguous or the conflict is between learned and manually edited guidance, ask one focused question before a durable change.

## Classify the correction

1. **Explicit ongoing preference.** Examples: “Stop ending every post with a question”; “Use British spelling in future drafts.” In explicit mode, save a narrow rule now and acknowledge it briefly. Do not turn “not every post” into “never ask questions.”
2. **Local edit.** Examples: “Remove this question”; a single edited paragraph; a fact correction. Revise that draft only. Do not infer a universal style rule, new expertise, or a lasting ban.
3. **Repeated pattern.** When the user supplies the original draft and their edited version, compare them. If the same narrow change appears in at least three distinct drafts, propose a preference and ask for confirmation. Never activate inferred patterns just because they repeat. Three is a conservative review trigger, not proof of intent.
4. **Context or authority change.** Identity, audience, product claims, results, privacy permissions, source access, and publishing permissions are not style learning. Route factual or identity updates through source checks and profile confirmation. Never learn authorization from an edit, engagement metrics, or a third-party writing sample.

Only user feedback about their drafts counts. Source documents, quoted text, references, assistant self-edits, likes, and performance metrics are not preference corrections. If only the edited version is available, use it for the current task; do not fabricate a comparison or record a counted observation.

## Record evidence without hoarding drafts

Use `.content-workspace/feedback-log.md`, starting from [the blank log](../templates/feedback-log.md). Keep records in the current author's selected working directory. Do not collect private excerpts, customer names, or full original/revised posts just to learn style. Store a minimal abstract summary and an existing source/draft ID.

Allocate a stable preference ID and change ID after reading existing records. Reprocessing the same correction is idempotent: update neither its count nor the profile again. Count at most once per distinct draft toward a proposed pattern. If draft identity is unclear, ask or leave it uncounted. Log rejected proposals so they are not repeatedly offered; reopen only for new explicit direction. Keep no more than 20 pending pattern summaries; summarize or discard obsolete pending observations, not the applied change history.

## Apply and verify a change

1. Re-read the profile and log immediately before writing. Work sequentially. If another writer has changed the relevant content, reconcile or ask before writing; do not overwrite it from an earlier snapshot.
2. Record a `planned` log entry with date, IDs, abstract source, scope, reason, and exact prior/new text for the affected rule. Do not snapshot the whole profile.
3. Change only the `Learned writing preferences` section, or the learning-mode field for a control request. Create the section if an older profile lacks it. Increment `profile_version` for an applied change, preserving all other fields.
4. Read back the profile. Only then mark the log entry `applied` and tell the user what changed in one short sentence outside the post copy.

If a write fails, report that the preference was not saved. On a later run, reconcile `planned` entries: if the rule matches the intended new text, finish marking it applied; if it matches the old text, leave the change unapplied and retry only while the original direction remains applicable; if neither matches, report a conflict. Never silently discard a manual edit or claim an unverified save.

For conversation-only use or unavailable writes, show the updated preference and change record in the conversation. Say it applies here and is not saved for future sessions. Supply an updated profile on request. Do not claim automatic persistence.

## Undo, forget, and pause

“Undo the last learned change” restores only the affected rule from the latest applied, non-reverted log entry. Verify the current text still matches that entry's new text. If it has changed, ask before overwriting. For a newly created rule, undo removes that rule. For a replaced rule, undo restores its old text. Preserve unrelated rules and fields. Increment the profile version and record the reversal as a new applied entry pointing to the original; mark the original reverted after verification. Do not reactivate rejected or reverted evidence automatically.

“Forget P001” removes that active preference and its retained observation summaries, and redacts its rule text and evidence from prior change records; keep only a redacted tombstone with its ID and removal date so replay cannot silently restore it. Do not claim deleted text can still be recovered. “Show learned preferences” returns active rules and scopes. “Pause learning” sets mode off. “Resume learning” restores explicit mode unless the user chooses review.

An undo or forget request does not rewrite already approved, scheduled, or published content. Offer a draft revision only when requested.
