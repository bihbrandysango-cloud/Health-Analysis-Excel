# How to publish this repo to GitHub

**READ THIS BEFORE UPLOADING.** The single most common mistake breaks every link in the README. This guide prevents that.

---

## The mistake that breaks every link

When you unzip `health-analysis.zip`, you get a folder called `health-analysis` containing all the project files (README, docs/, workbook/, etc.).

**Do not upload the `health-analysis` folder itself to your GitHub repo.** Upload the **contents** of that folder.

### What broken looks like

```
your-github-repo/
└── health-analysis/        ❌ EXTRA FOLDER — every link breaks
    ├── README.md
    ├── docs/
    └── workbook/
```

### What correct looks like

```
your-github-repo/
├── README.md               ✅ At the root
├── docs/
└── workbook/
```

Every link in the README assumes the second layout. If you have the first layout, every link points to a path that doesn't exist.

---

## Path A: Upload through the GitHub website (no command line)

### Step 1: Create the repository

1. Sign in to https://github.com
2. Click the green **New** button (top left)
3. **Repository name:** `health-analysis`
4. **Description:** *Healthcare data, turned into decisions. Two years of patient visit and cost data, cleaned and shaped into an Excel dashboard.*
5. **Visibility:** Public
6. Leave everything else unchecked
7. Click **Create repository**

### Step 2: Unzip and prepare

1. Download `health-analysis.zip`
2. Unzip it — you now have a folder called `health-analysis` on your computer
3. **Open that folder.** Inside you should see: `README.md`, `LICENSE`, `CONTRIBUTING.md`, `GITHUB-SETUP.md`, `.gitignore`, `docs/`, `workbook/`

### Step 3: Upload the contents (not the folder)

1. On the new empty repo page on GitHub, click **uploading an existing file**
2. **Inside** the unzipped `health-analysis` folder on your computer, press **Ctrl+A** (Windows) or **Cmd+A** (Mac) to select every file and subfolder
3. Drag that selection onto the GitHub upload area
4. **Verify the file list shown by GitHub.** You should see `README.md`, `LICENSE`, `CONTRIBUTING.md`, `docs`, `workbook`, etc. listed individually — NOT a single folder called `health-analysis`
5. If you see `health-analysis` as the only item, **stop**. You uploaded the folder instead of its contents. Cancel and try again.
6. At the bottom, write: `Initial commit`
7. Click **Commit changes**
8. Wait for upload (the Excel file is ~37MB, takes a minute)

### Step 4: Verify it worked

1. Refresh your repo page
2. The README should render with the dashboard hero image visible
3. The file list above the README should show `docs`, `workbook`, `LICENSE`, etc. directly — no wrapper folder
4. Click the **docs** folder — you should see the PDF, PPTX, and a `screenshots` subfolder
5. Click the **workbook** folder — you should see `Health_Analysis.xlsx`
6. Back on the main README, click any dashboard image — it should open the full-size JPG
7. Click the **Read the documentation (PDF)** link — it should preview the PDF inline

If all six checks pass, you're done.

---

## Path B: Use Git from the command line

### Step 1: Create the empty repository on GitHub

Same as Path A, Step 1. Do not initialize with any files.

### Step 2: Push from your machine

```bash
cd path/to/health-analysis          # cd INTO the unzipped folder, not its parent
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/<YOUR-USERNAME>/health-analysis.git
git push -u origin main
```

Critical: the `cd path/to/health-analysis` must put you **inside** the unzipped folder. If you run `git init` from the parent directory, you'll commit the wrapper folder and break every link.

### Step 3: Verify

Same as Path A, Step 4.

---

## If links are still broken after upload

Run through this checklist in order. Stop at the first one that's wrong.

### Check 1: Is the README at the root of your repo?

Visit `https://github.com/<your-username>/health-analysis` (your repo's main page).

- ✅ Correct: README content displays directly under the file list
- ❌ Broken: You see only a folder called `health-analysis` and nothing else, OR the README only shows if you click into a subfolder

**Fix:** Delete the wrapper folder by clicking into it, then re-uploading the contents at the root.

### Check 2: Are the dashboard images broken?

Look at the README on your repo page. Do you see the dashboard charts, or do you see broken-image placeholders?

- ✅ Working: Charts render inline
- ❌ Broken: You see broken-image icons

**Fix:** Click into `docs/screenshots/` in your repo. Confirm all 7 JPG files are there: `01-executive-overview.jpg` through `06-monthly-visits.jpg` and `hero.jpg`. If any are missing, drag-upload them to that folder.

### Check 3: Do the PDF and Excel links 404?

Click the **Read the documentation (PDF)** link in your README.

- ✅ Working: GitHub shows the PDF preview, or a file page with a Download button
- ❌ Broken: You see a GitHub 404 page

**Fix:** The file path in the link doesn't match where the file lives in your repo. Check `docs/Health-Analysis-Documentation.pdf` exists by clicking into `docs/` on your repo page.

### Check 4: Build absolute URLs as a last resort

If checks 1-3 all look correct but links still fail, you can rewrite every relative link to use the full GitHub URL. Replace this pattern in the README:

- Find: `(docs/Health-Analysis-Documentation.pdf)`
- Replace: `(https://github.com/<YOUR-USERNAME>/health-analysis/blob/main/docs/Health-Analysis-Documentation.pdf)`

Do this for every internal link. Tedious but bulletproof. The included README uses relative links because they're cleaner and they work when the structure is correct.

---

## After publishing

### Add it to your LinkedIn Featured section

1. Go to your LinkedIn profile
2. Open the **Featured** section
3. Click **+** then **Link**
4. Paste the GitHub repo URL: `https://github.com/<your-username>/health-analysis`
5. LinkedIn auto-pulls the README hero image as the preview

### Pin it on your GitHub profile

1. Go to your GitHub profile page
2. Click **Customize your pins** (top right of repositories section)
3. Check `health-analysis`
4. Click **Save**

The repo will show on your profile as a featured project.

---

## Questions

If something still won't work after this guide, open the repo page, click any broken link, copy the URL from your browser bar, and email it with a screenshot to Bihbrandy15@gmail.com.
