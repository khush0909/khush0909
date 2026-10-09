# Khush's GitHub portfolio — setup guide

This zip has **5 folders. Each folder becomes one GitHub repository** — the repo name must match the folder name exactly.

Everything is filled in already: email, LinkedIn, KPMG experience, and `resume.pdf` in the website folder.

| Folder / repo name | What it is |
|---|---|
| `khush0909` | **Profile README** — shows at the top of github.com/khush0909 |
| `khush0909.github.io` | **Portfolio website** — goes live at https://khush0909.github.io |
| `superstore-sales-analysis` | Project 1 — Python + Excel + Power BI |
| `olist-ecommerce-sql-analysis` | Project 2 — SQL |
| `hr-attrition-analysis` | Project 3 — Python + Tableau |

---

## Step 1 — Create the 5 repositories

For each folder: on GitHub click **+ → New repository** → type the folder name → **Public** → don't add a README → **Create**.

> `khush0909` is GitHub's special profile repo: GitHub will say *"You found a secret!"* — that's expected.

### Option A — upload in the browser (easiest)
1. Open the new empty repo → click **uploading an existing file**.
2. Open the folder on your computer, select **everything inside it** (not the folder itself) and drag it in. Sub-folders upload too in Chrome/Edge.
3. Click **Commit changes**.

> In `olist-ecommerce-sql-analysis` the 8 Olist CSVs are deliberately **not** included (they're ~60 MB). `scripts/build_database.py` downloads them automatically.

### Option B — Git (better: shows real commit history)
```bash
cd superstore-sales-analysis
git init
git add .
git commit -m "Superstore sales and profitability analysis"
git branch -M main
git remote add origin https://github.com/khush0909/superstore-sales-analysis.git
git push -u origin main
```
Repeat for each folder with its own repo name.

## Step 2 — Turn on the website

`khush0909.github.io` repo → **Settings → Pages** → Source: **Deploy from a branch** → Branch: **main**, folder **/ (root)** → **Save**.
After 1–2 minutes the site is live at **https://khush0909.github.io**.

## Step 3 — Polish the profile page

1. **Profile → Edit profile**
   - Bio: `Aspiring Data Analyst | Python, SQL, Excel, Power BI, Tableau | B.Tech CSE @ LPU`
   - Website: `https://khush0909.github.io`
   - Add LinkedIn under social accounts
2. **Pinned repos → Customize your pins** → pin the 3 projects + `khush0909.github.io`. Unpin *Tables-from-2-to-n-number*, *Property-Website-HTML* and the prime-number fork.
3. On each project repo, click the ⚙️ next to **About** and paste:

| Repo | Description | Topics |
|---|---|---|
| superstore-sales-analysis | Retail profitability analysis in Python, Excel and Power BI — found $135K lost to heavy discounts | `data-analysis` `python` `pandas` `excel` `power-bi` `eda` |
| olist-ecommerce-sql-analysis | SQL analysis of 100K e-commerce orders — CTEs, window functions, RFM, delivery vs reviews | `sql` `sqlite` `data-analysis` `window-functions` `rfm-analysis` |
| hr-attrition-analysis | Employee attrition drivers and an at-risk employee list with Python and Tableau | `hr-analytics` `python` `pandas` `tableau` `data-analysis` |
| khush0909.github.io | My data analyst portfolio | `portfolio` |

   Also set **Website** in each About box to `https://khush0909.github.io`.
4. Optional: **archive** old beginner repos (Settings → Archive) or delete the forked one, so the profile reads as a data analyst's.

## Step 4 — Build the two BI dashboards (do this yourself)

These need desktop apps, so they're step-by-step guides rather than finished files:

- **Power BI** → `superstore-sales-analysis/powerbi/README.md` (~1.5–2 h). Save the `.pbix` in that folder, add screenshots to `images/`, then remove the `<!--` `-->` around the screenshots in the project README.
- **Tableau Public** → `hr-attrition-analysis/tableau/README.md` (~1.5–2 h). Publish it, paste the public link into the project README and the website.

The website and profile list Power BI and Tableau as skills, so **build both dashboards before sharing the links with recruiters**.

## Step 5 — Before any interview

Open each notebook in Jupyter, **run every cell yourself, and make sure you can explain each step and each number** —
interviewers *will* ask "why did you do this?" and "what does this query do?". Changing a chart, adding a question of
your own, or redoing one analysis in a different tool is the best way to make the work genuinely yours.

```bash
pip install -r requirements.txt
jupyter notebook
```

For the SQL project run `python scripts/build_database.py` first.
