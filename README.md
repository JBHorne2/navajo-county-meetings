# Navajo County, AZ — Meeting Archive (text corpus)

Machine-readable text mirror of every available agenda, minutes document, and
meeting transcript for three Navajo County public bodies:

| Body | Folder | Coverage |
|------|--------|----------|
| Board of Supervisors | `docs/BOS/` | 2003–present |
| Board of Adjustment | `docs/BOA/` | 2010–present |
| Planning & Zoning Commission | `docs/PZ/` | 2011–present |

## Layout

- `docs/<BODY>/<YEAR>/<date>_<body>_<doctype>_<id>.md` — one markdown file per document.
- `index.csv` — master index: date, body, doc_type, extraction quality, path.

Each document begins with YAML frontmatter:

```yaml
body: Board of Supervisors
date: 2020-06-23
doc_type: minutes          # agenda | agenda-packet | minutes | transcript
source_system: destiny     # civicplus | destiny | swagit
source_file: NavajoCountyAgendas/BOS/2020/...   # original file on archive machine
extraction: ok             # ok | poor-likely-scanned
```

## Document types

- **agenda** — the published meeting agenda.
- **agenda-packet** — agenda plus all attachments/backup material (2017+, often hundreds of pages).
- **minutes** — official minutes. PDFs through ~2023; HTML-sourced for Destiny-era meetings.
- **transcript** — unedited machine voice-to-text of the meeting video (Swagit, Jan 2024+).
  Not the official record; useful for verbatim discussion.

## Provenance

Sources: Navajo County CivicPlus AgendaCenter (`navajocountyaz.gov/AgendaCenter`),
Destiny Hosted / AgendaQuick (`public.destinyhosted.com`, site id 62825), and
Swagit video transcripts (`navajocountyaz.new.swagit.com`). All public records.
Text extracted from source PDFs/HTML; `<!-- page N -->` comments mark original
PDF page boundaries. A small number of documents are flagged
`extraction: poor-likely-scanned` where the source was image-based.

Known gaps: three BOS agenda packets (2025-01-14, 2025-10-14, 2026-01-13) are
corrupt on the county's server; the plain agenda HTML is included instead.
Meetings during 2020–2023 were held or streamed via Zoom and have no public
video/transcript. Original binary archive (PDFs) lives on the archive machine in
the `NavajoCountyAgendas\` folder alongside the collection scripts, downloaded
via `Download-NavajoAgendas.ps1` and `Download-NavajoTranscripts.ps1`.
