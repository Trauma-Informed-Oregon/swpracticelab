# SW 510 Practice Lab

An optional, ungraded practice lab for SW 510, AI in the Helping Professions (Portland State University School of Social Work). It is one HTML file. It has no build step, no external requests, no analytics, and no storage, so it keeps working offline and can be copied and reused without any setup.

## What is in it

- **Start here: The Life and the Record.** A simulation that follows one fictional person through a scoring system and shows what each step keeps and loses. Students change design choices and see the outcome, cost, privacy risk, and trust change.
- **Labs 1 to 9.** Practice activities tied to the course weeks, each reshaping itself around one of five professional lenses (Labs 1 to 7).
- **Practice Scan Starter.** Eight questions to ask of any system, sorted into what is known, what needs finding out, and what raises concern.
- Watch and explore links, practice notes (kept only on the page), and a plain-language glossary.

## Make your own scenario for The Life and the Record

The simulation reads the JSON block with `id="scenario-data"`. On the Start here page, open "Build your own person" to edit, load, and download a scenario without touching the code. Use invented people only.

Top level: `title`, `person` (`name`, `line`), `system`, `truths`, `levers`, `presets`.

- `system`: `base` (starting score), `cutoff`, `perPoint`, `cap`, `countIds` (truth ids that earn points once the score reads them), `scoreFields` (plain description of what the score uses), `baseReshape` (truth id to the reduced text the record holds by default), `accommodationIds` (truth ids the record must hold for the contact to work).
- `truths`: `id`, `label`, `text`, `relevant` (true if it bears on the person's need), `sensitive` (true if recording it could harm the person).
- `levers`: `id`, `stage` (1 to 6), `label`, `detail`, `cost`, `risk`, and any of these effects: `adds` (truth ids brought into the record), `personChooses` (the person can keep sensitive, irrelevant items out), `community` (the score counts circumstances that raise need), `band` (points below the cutoff that trigger a second look), `reviewOverride` (number of relevant truths a reviewer needs to change the result), `informs` (the person is told and can decline).
- `presets`: `label` and `on` (list of lever ids).

## Accessibility

Keyboard operable, labelled controls, no color-only meaning (every card carries a text label), respects reduced motion, prints cleanly. Checked with axe-core on every section at desktop and phone width.

## License

Add a license before sharing outside the course.

## Tool Bench

Six working tools, each with fictional data and a real model running in the browser. Nothing is sent anywhere.

| Tool | Engine | What the student does |
|---|---|---|
| Outreach priority list | Logistic regression trained on 800 synthetic people, audited on 600 held out | Choose facts and labels, set capacity, read false-alarm rates by group, compare with a simple rule and a random draw |
| Session note scribe | Extractive scorer with a visible vocabulary | Audit what a draft kept and dropped, repair it, count review time |
| Benefits case reader | Rules over 300 synthetic applications with document-dependent reading error | Set cutoffs, see who waits, meet a challenge |
| Message assistant | Naive Bayes message sorter trained on 56 examples, tested on 29 held-out messages | Test crisis detection by writing style, add training examples, check policy practices |
| Paste check | Pattern filter plus a 2,400-person synthetic town | See what a filter misses and how many residents a note still describes |
| Vendor desk | Accuracy calculator and a 14-clause contract review | Test a headline claim with real arithmetic, rate clauses, get a vendor profile |

Every tool follows the same path: predict, operate, open the hood, compare with a simpler option, then write a recommendation (use, limit, redesign, pause, or reject) that the page drafts from the student's own numbers and sends to My practice notes. Tools are tagged to the course objectives they practice. The anchors on each tool cite current sources (ONC 2024, Nextgov 2026, Fierce Healthcare, News From The States, Morgan Lewis, NASW Illinois, Holland & Knight).

These are teaching models, not vendor products. Their numbers describe the simulations only.
