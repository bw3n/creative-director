# Campaign Log

This log tracks every campaign the scanner has processed. Read this before fetching a URL or running the cron — prevents duplicate processing.

## Status key

- `pending` — draft card exists in `incoming/campaigns/`, awaiting your review
- `accepted` — moved to `references/campaigns/`, part of the corpus
- `rejected` — declined for the corpus, draft deleted

## Campaigns

| Slug | Status | Medium | Date | Images | Drive Folder |
|------|--------|--------|------|--------|--------------|
| burger-king-leave-the-flame-grilling-to-us | pending | Print | 2026-08-08 | 5 | [ADs]/Print/burger-king-leave-the-flame-grilling-to-us/ |
| uae-open-invitation-for-creatives-in-cannes-lions-2026 | pending | Print | 2026-08-08 | 3 | [ADs]/Print/uae-open-invitation-for-creatives-in-cannes-lions-2026/ |
| polaroid-the-best-of-summer-is-analog | pending | OOH | 2026-08-08 | 6 | [ADs]/OOH/polaroid-the-best-of-summer-is-analog/ |
| bhavya-ramesh-jewelry-stare | pending | Film | 2026-08-08 | 4 | [ADs]/Film/bhavya-ramesh-jewelry-stare/ |
| royal-society-for-blind-children-bedtime-donations-campaign | pending | Digital | 2026-08-08 | 4 | [ADs]/Digital/royal-society-for-blind-children-bedtime-donations-campaign/ |
| wwf-fire-on-display | pending | OOH | 2026-08-08 | 4 | [ADs]/OOH/wwf-fire-on-display/ |
| painvisible-campaign-by-aritium | pending | Tech | 2026-08-08 | 1 | [ADs]/Tech/painvisible-campaign-by-aritium/ |

---

## How the log is used

**Cron check:** At the start of each daily scan, the script reads this log. For each candidate URL from the COTW index, if the slug appears with status `accepted`, `rejected`, or `pending`, the script skips it.

**One-off check:** When you send me a URL, I read this log first. If the slug appears, I tell you the current status instead of re-processing.

**Updates:**
- Scanner creates draft → append row with status `pending`
- You accept a draft → I update status to `accepted` and add the corpus path
- You reject a draft → I update status to `rejected`

## Maintenance

This file is hand-curated. The scanner reads it; it doesn't auto-edit it. If rows get out of sync (manual moves, deletes), regenerate from filesystem:

```bash
ls incoming/campaigns/*.md | xargs -n1 basename
```
