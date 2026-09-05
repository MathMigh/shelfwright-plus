# Shelfwright Plus — Author Mode v0.3

An additive extension for Shelfwright. It does **not** replace or delete Shelfwright's existing search, browser, queue, naming, sync or desktop UI.

Pinned upstream: `fb536b6584f1cc49c6b6ad6cb68f7ca42d9860b8`.

## Main additions

- Author mode: author → unique works, instead of one row per edition/ISBN.
- Internet Archive integration with structured metadata search and public-file inspection.
- Persistent SQLite catalogue for authors, works and source locations.
- Public Internet Archive fallback when the original worker cannot obtain a file and an ordinary public copy exists on Archive.
- Optional Vercel companion for author discovery, unique-work browsing and Internet Archive search.
- Optional Google Drive for Desktop destination mirroring.

## Design rule

**Upstream first. Plus second.** Shelfwright remains the foundation; Plus adds capabilities around it rather than rewriting the original project.

## Vercel

The `vercel/` directory is designed to be deployed as the Vercel Root Directory. It contains the public web companion for Open Library + Internet Archive. The persistent desktop worker remains local because it needs long-running state, local files and an interactive browser session.

## Boundaries

Automatic acquisition in the Plus layer is limited to ordinary public/downloadable files or files the user is otherwise entitled to obtain. Other connectors may catalogue and locate records without bypassing access controls.
