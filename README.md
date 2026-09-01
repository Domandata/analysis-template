# Analysis template

This repo is created automatically for you by Domandata's GitHub Sync feature. It exists so
your analysis pipeline always has a fresh copy of your survey's response data without any
manual export/upload step.

## What's here

- `data/responses.csv` or `data/responses.json` — auto-updates on a schedule (every 15
  minutes) via the GitHub Action in `.github/workflows/sync-data.yml`. You can also trigger
  a sync immediately from this repo's **Actions** tab using "Run workflow".
- `.github/workflows/sync-data.yml` — the sync workflow itself. You shouldn't need to edit
  this file; it was configured automatically when the repo was created (its `SURVEY_ID`,
  `PII_MODE`, `EXPORT_FORMAT`, `EXPORT_LABELS`, and `EXPORT_FLAT` variables, plus its
  `DOMANDATA_API_KEY` secret, are already set).

## Notes

- This repo is always private.
- By default, free-text and other identifying answer types (short answer, signature, file
  upload, audio interview, text chat) are excluded from the synced data. This can be changed
  per-survey from the GitHub Sync card in Domandata's Deploy tab.
- Export format, label mode, and JSON flattening follow the Advanced GitHub Sync settings in
  Domandata Workspace Settings.
- Deleting a response in Domandata does not remove it from this repo's prior commits — only
  from future syncs.
