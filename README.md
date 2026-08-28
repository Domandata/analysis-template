> **Note:** This folder is a local staging area for the contents of a *separate* GitHub
> repository — `domandata/analysis-template` — the actual template that Domandata's GitHub
> App clones from when a researcher clicks "Create Repo" in the Deploy tab. It is not part
> of this Next.js application, is not imported by any app code, and is not built, linted, or
> type-checked as part of this repo's pipeline. It lives here only because there's nowhere
> else in this codebase to keep it under version control until it's pushed to that separate
> repo.

# Analysis template

This repo is created automatically for you by Domandata's GitHub Sync feature. It exists so
your analysis pipeline always has a fresh copy of your survey's response data without any
manual export/upload step.

## What's here

- `data/responses.csv` — auto-updates on a schedule (every 15 minutes) via the GitHub Action
  in `.github/workflows/sync-data.yml`. You can also trigger a sync immediately from this
  repo's **Actions** tab using "Run workflow".
- `.github/workflows/sync-data.yml` — the sync workflow itself. You shouldn't need to edit
  this file; it was configured automatically when the repo was created (its `SURVEY_ID` and
  `PII_MODE` variables, and its `DOMANDATA_API_KEY` secret, are already set).

## Notes

- This repo is always private.
- By default, free-text and other identifying answer types (short answer, signature, file
  upload, audio interview, text chat) are excluded from the synced data. This can be changed
  per-survey from the GitHub Sync card in Domandata's Deploy tab.
- Deleting a response in Domandata does not remove it from this repo's prior commits — only
  from future syncs.
