# 🇪🇹 EUEE 24-Week Study Planner

A local-first, offline-capable study planner for Ethiopian Grade 11 students preparing for the EUEE.
Organises preparation across Grades 9–12 curriculum + mixed revision + past-paper practice over 24 weeks.

## Important academic disclaimer

This planner **does not predict** the actual EUEE exam.
Labels like **HIGH PRIORITY** are study-priority estimates based on historical frequency, curriculum importance, or user-imported verified data.
They are **not** guarantees that any topic will appear on the future exam.

No EUEE questions, answers, exam years, textbook pages or frequencies are shipped with this app.
You must import **verified** data yourself.

## Quick start

```bash
# Option 1: no install — open index.html directly in a browser
# Option 2: use a local server
python -m http.server 8000
# then visit http://localhost:8000

# Option 3: Vite dev server
npm install
npm run dev
```

### Production build

```bash
npm run build       # outputs to dist/
npm run preview     # serves the build locally
```

## Adding verified EUEE data

1. Go to **Data Import** in the sidebar.
2. Prepare a CSV with columns:
   ```
   year,ec_year,stream,subject,grade,unit,topic,question_number,question,choice_a,choice_b,choice_c,choice_d,correct_answer,explanation,difficulty,source
   ```
   Or a JSON array with the same keys.
3. Click **Import EUEE file**. Invalid rows are skipped and reported.
4. Go to **EUEE Questions** to browse, **Practice Exam** to practise.

## Adding verified curriculum data

1. Go to **Data Import**.
2. Prepare a CSV with columns:
   ```
   grade,stream,subject,unit,chapter,topic,subtopic,learning_objective,key_concepts,page,source
   ```
3. Click **Import curriculum file**.

## Data integrity

- Never import unverified EUEE questions, answers, or exam years.
- Fields without a source are stored as **"Unverified"** / **"Needs source"**.
- The analysis page only computes figures from your imported, verified data.

## Architecture

```
index.html          — full single-page app (HTML + CSS + JS)
package.json        — scripts for optional Vite dev server
README.md           — this file
data/               — (optional) place canonical JSON you may want to load
```

- Vanilla JS — no framework required.
- `localStorage` keys: `euee_progress_v1`, `euee_errors_v1`, `euee_practice_v1`, `euee_notes_v1`, `euee_streak_v1`, `euee_curriculum_v1`, `euee_questions_v1`, `euee_english_v1`, `euee_aptitude_v1`, `euee_settings_v1`.
- Chart.js is loaded from a CDN and cached by the browser.

## Features

- Dashboard with week, phase, progress bar, streak, today's routine
- 24-week plan with per-subject checkboxes
- Clickable topic cards with notes, priority, and linked EUEE questions
- EUEE question database with filters (grade, subject, year, difficulty, search)
- Practice Exam: choose subject/year/topic/count/difficulty/timed → auto-scored, mistakes pushed to Error Log
- Topic Analysis with charts (by subject, grade, year, difficulty) + study-priority estimates
- Error Log with mistake types, retest & mastery flags
- English & Aptitude trackers
- Global search
- CSV / JSON import + export
- Offline-first, mobile-first design
- Streak system (informational only — no notifications)

## License

For personal educational use.
