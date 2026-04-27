# JobsToPR Website

Live: https://jobstopr.me

## What's Here

- `index.html` — The complete one-page website (HTML + CSS + JS embedded)
- `CNAME` — Tells GitHub Pages to use jobstopr.me as the custom domain

## How to Deploy (First Time Setup)

### Step 1 — Create a GitHub Repository
1. Go to github.com → click "+" → New repository
2. Name it: `jobstopr` (lowercase)
3. Set it to **Public**
4. Don't add README, .gitignore, or license — just create empty
5. Click "Create repository"

### Step 2 — Upload the Files
1. On the new empty repo page, click "uploading an existing file"
2. Drag and drop both files: `index.html` and `CNAME`
3. Scroll down → click "Commit changes"

### Step 3 — Enable GitHub Pages
1. Click **Settings** tab on the repo
2. Click **Pages** in the left sidebar
3. Under "Source," select **Deploy from a branch**
4. Branch: `main` → Folder: `/ (root)` → click Save
5. Wait 1-2 minutes — GitHub will give you a URL like `https://yourusername.github.io/jobstopr/`

### Step 4 — Connect jobstopr.me Custom Domain
1. In the same Pages settings, find "Custom domain"
2. Enter: `jobstopr.me` → click Save
3. GitHub will check DNS — this might take a few minutes

### Step 5 — Configure DNS at Namecheap
1. Log into Namecheap → Domain List → Manage jobstopr.me
2. Go to **Advanced DNS** tab
3. Delete any existing A or CNAME records
4. Add these records:

   **A Records (4 entries):**
   - Host: `@` → Value: `185.199.108.153`
   - Host: `@` → Value: `185.199.109.153`
   - Host: `@` → Value: `185.199.110.153`
   - Host: `@` → Value: `185.199.111.153`

   **CNAME Record (1 entry):**
   - Host: `www` → Value: `YOURUSERNAME.github.io` (replace with your actual GitHub username)

5. Save changes
6. Wait 10 minutes to 24 hours for DNS to propagate

### Step 6 — Force HTTPS
1. Back in GitHub Settings → Pages
2. Once DNS is verified, check the box "Enforce HTTPS"

## How to Update the Site Later

Just edit `index.html` on GitHub directly:
1. Go to your repo → click on `index.html`
2. Click the pencil icon (Edit)
3. Make changes
4. Scroll down → "Commit changes"
5. Site updates within 1-2 minutes

## Connecting Tally Form (Critical Next Step)

1. Build your Tally form at tally.so
2. After publishing, copy the form URL (looks like: `https://tally.so/r/XXXXX`)
3. Open `index.html` in GitHub
4. Search for: `function openForm()`
5. Replace this line:
   ```javascript
   alert('The Tally form will be connected here...');
   ```
   With this line:
   ```javascript
   window.open('https://tally.so/r/YOUR_FORM_ID', '_blank');
   ```
6. Commit changes — form is now live

## Connecting Product Buttons (When Gumroad Is Ready)

Each product button has `href="#"` — replace with actual Gumroad/payment URLs:
- Mini Kit button: replace `href="#"` with your Gumroad Mini Kit URL
- Starter Kit button: replace with Starter Kit URL
- Premium Kit button: replace with Premium Kit URL
- 1-on-1 button: replace with Calendly booking URL
