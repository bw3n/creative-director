# creative-director

A creative-director asset system: campaign corpus, principles, vocabulary, brief critique, ideation.

**Repo:** `bw3n/creative-director`
**Local path:** `~/creative-director-skill/` (the VPS clone)
**Synced across:** Mac (Obsidian), Windows PC (Obsidian), work laptop (TBD)

## Structure

```
creative-director/
├── README.md                           ← this file
├── SKILL.md                            ← the skill (5 jobs: brief-critique, ideation, brainstorm, art-direction, work-critique)
├── incoming/                           ← draft cards awaiting your review
│   ├── .gitignore                      ← excludes images/ and scan.log from git
│   ├── campaigns/                      ← draft campaign cards (skeleton fields, body at the bottom)
│   ├── images/                         ← local copies of campaign images (gitignored)
│   └── scan.log                        ← COTW scanner activity log
├── references/                         ← the live corpus
│   ├── index.md                        ← one-line entry per campaign
│   ├── campaigns/                      ← finished campaign cards (full reasoning)
│   ├── principles/                     ← one file per principle of art direction
│   └── vocabulary/                     ← vocabulary patterns
├── examples/                           ← worked examples of the 5 jobs
└── sessions/                           ← scrap-session notes (added over time)
```

## How the corpus grows

1. **COTW scanner** runs daily at 6 AM SGT. It fetches the latest ad from each of 5 categories (Film, Digital, OOH, Tech, Print) on campaignsoftheworld.com, downloads the images, writes a draft card to `incoming/campaigns/`, and uploads the images to your Google Drive at `[ADs]/<Medium>/<brand-name>/` with a README.

2. **You review drafts.** Open `incoming/campaigns/` in Obsidian. Read the article body at the bottom of the card, look at the Drive images (click the URLs in Visual examples), decide whether to keep the campaign.

3. **To accept:** tell me ("accept carlsberg-goal-posters"). I fill in the empty fields based on the article body, move the card to `references/campaigns/`, update `references/index.md`, push to GitHub.

4. **To reject:** tell me ("reject marmite-wemite-campaign"). I delete the draft card from `incoming/campaigns/`. You delete the Drive folder manually when convenient.

## Devices

Synced via GitHub to:
- Mac (Obsidian + Obsidian Git plugin) — primary
- Windows PC (Obsidian + Obsidian Git plugin)
- Work laptop (TBD)

The COTW scanner runs on the VPS and writes to this repo. Your Mac pulls via Obsidian Git on a 5-minute cron.

## COTW scanner

A Python script (`cotw_scan.py`) on the VPS that:
1. Fetches each COTW category page (stealth mode, bypasses Cloudflare).
2. Extracts the latest article URL from each category.
3. Fetches the article, parses metadata (title, date, image URLs).
4. Downloads images to `incoming/images/<slug>/`.
5. Uploads images to Drive at `[ADs]/<Medium>/<slug>/` with a README.
6. Writes a draft card to `incoming/campaigns/YYYY-MM-DD-<slug>.md` with Drive URLs in the Visual examples section.

Cron entry: `0 22 * * * python3 /home/ubuntu/bin/cotw_scan.py >> /home/ubuntu/creative-director-skill/incoming/scan.log 2>&1`

## Draft card format

The scanner writes skeletons — most reasoning fields are empty. The article body is at the bottom (so you have the source material). To card:

1. Read the article body.
2. Fill in: What it was trying to do, The tension, The visual mechanism, The refusal, What to steal, What not to steal.
3. Move from `incoming/campaigns/` to `references/campaigns/`.
4. Add a one-line entry to `references/index.md`.
5. Push to GitHub.