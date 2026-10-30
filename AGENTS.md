# AGENTS.md

Varun Ayyappan's portfolio, a GitHub Pages user site at https://varunayyappan.github.io. It was scaffolded from v2.0.1 of his [Nord Portfolio Astro Theme](https://github.com/VarunAyyappan/Nord-Portfolio-Astro-Theme), so `README.md` (still the Theme's) documents every content file, Site config field and deploy step.

Deploy publishes on every push to `main`, so work on a branch until the content is real. Before committing, run `aube run check` and `aube exec biome ci`.

## Replacing the filler content (in progress)

We're going through the content one point at a time: Claude proposes a draft, Varun edits or approves it, then Claude writes it in. Delete this section once the site is live.

### Done

- `src/site.config.ts`: name, tagline, intro, `availability: "open"`, `base: "/"`.
- Skills: Languages, Machine learning, Data. List only what Varun can defend in an interview. Every skill so far is backed by code in his class repos (below), and anything without evidence was dropped.

### Next

1. **Skills, rest:**
   - **AI engineering** group, from CSE 598 Agentic AI at ASU, which isn't in the class repos (syllabus of a later run: https://labs.engineering.asu.edu/hw/teaching), and from anything he's done on his own.
   - **Tools** group, candidates found in his class repos: Django, Flask, SQLite (CMSC 435), PostgreSQL via psycopg (CMSC 424), D3.js (CSE 578), ROS (CSE 598 PiR), plus Git, Linux and Astro.
2. **Social links** in Site config.
3. **Experience and education**, in `src/content/experience/`, `src/content/education/`:
   - BS Computer Science, University of Maryland, May 2024, with minors in Statistics and History.
   - MS Computer Science, Arizona State University, May 2026.
   - A coursework line, such as CMSC 330, may fit.
4. **Projects**, candidates from his class repos:
   - The CSE 598 Agentic AI capstone and Codex CLI source-reading reports, if his semester had them.
   - The CSE 575 group project (fine-tunes BART).
   - The CMSC 435 ticket system (Django with GPT-3).
   - FireCOML.
   - This site and the Theme.
5. **About and Contact**: bio, `openTo`, timezone (he's in San Jose), and a portrait and PGP key, or remove both.
6. **`public/` files**: `resume.pdf` and `favicon.svg` (lint needs a `<title>`). Generate `share.png` if he has none.
7. **Blog**: delete the filler Posts. Drop Blog from `navigation` if he has no Posts yet.
8. **Finish**: rewrite `README.md` for the site, update or delete the tests that depend on the filler content (README, "Replacing the filler content"), then merge to `main`, which deploys.

### Class repos

His class project code is in two private repos:
- `VarunAyyappan/UMD`, his BS.
- `VarunAyyappan/ASU`, his MS, first year only.

Both are large, so shallow-clone them into a scratch directory, skipping big files, and grep them to check a skill or describe a project:

```sh
git clone --depth 1 --filter=blob:limit=1m git@github.com:VarunAyyappan/UMD.git
```

`UMD/CMSC424/assignment9Dist/spark-3.0.1-bin-hadoop2.7/` is a vendored copy of Spark, so leave it out of any search.
