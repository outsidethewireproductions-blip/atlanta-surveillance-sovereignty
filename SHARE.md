# Publish to GitHub, then deploy via Vercel

This folder contains everything needed for a public deployment. No build step. Static HTML.

**Files:**
- `atlanta-transparency-ledger.html` — the dashboard
- `index.html` — auto-redirect so the root URL serves the dashboard
- `vercel.json` — security headers and clean-URL routing for Vercel
- `SHARE.md` — this guide

The walkthrough below takes about five minutes end to end. I cannot push commits or click Deploy on your behalf because both actions are tied to your accounts and my operating rules prohibit modifying your access controls or creating accounts. The instructions are exact — you do the clicks, the dashboard goes live.

---

## Step 1. Create the GitHub repository.

Sign in at https://github.com. If you do not have an account yet, create one — that step is yours.

Open https://github.com/new in a new tab. Fill in:

- **Repository name**: `atlanta-surveillance-sovereignty` (or any name you like — this becomes part of your URL).
- **Description**: `Citizen-facing transparency dashboard for municipal surveillance access. Phase 01 reference implementation.`
- **Visibility**: Public.
- Leave "Add a README" unchecked. We already have SHARE.md and the dashboard.
- Leave .gitignore and license at None.

Click **Create repository**.

## Step 2. Upload the four files.

You will land on an empty repo page. Click the **uploading an existing file** link in the body text (or use the green **Add file** button → **Upload files**).

Open this folder in Finder:

`/Users/torrancesaunders/Documents/Claude/Projects/Project Community Surveillance Sovereignty/`

Drag these four files onto the GitHub upload page:

- `index.html`
- `atlanta-transparency-ledger.html`
- `vercel.json`
- `SHARE.md`

Scroll down. Commit message: `Initial Phase 01 dashboard`. Leave "Commit directly to the main branch" selected. Click **Commit changes**.

## Step 3. Connect Vercel.

Open https://vercel.com in another tab. Sign in or sign up. Vercel offers free hosting with a generous bandwidth allowance — no credit card required for the Hobby tier.

If this is your first time on Vercel, the easiest path is to sign in with GitHub. That auto-grants Vercel read access to your repos.

Once signed in, click **Add New** in the top right → **Project**. Vercel shows a list of your GitHub repositories. Find `atlanta-surveillance-sovereignty` and click **Import**.

On the configure-project screen:

- Framework preset: **Other** (Vercel auto-detects static sites).
- Root directory: leave at `./`.
- Build command: leave empty.
- Output directory: leave empty.
- Install command: leave empty.

Click **Deploy**. Vercel takes 30 to 60 seconds. When it finishes, you get a green confirmation and a URL like:

`https://atlanta-surveillance-sovereignty.vercel.app`

That is your live public link. Visit it once to verify the dashboard renders, the satellite map loads, and the live activity dots animate. Share the URL.

## Step 4 (optional). Custom domain.

If you own a domain — for example `outsidethewireproductions.com` — go to your Vercel project → **Settings** → **Domains** → **Add**. Enter the domain you want to attach. Vercel walks you through the DNS records you need to add at your domain registrar. Once DNS propagates (usually under an hour), your dashboard answers at the custom URL with a free TLS certificate.

## Step 5. Future updates.

Any time you change `atlanta-transparency-ledger.html` and push the new version to GitHub (drag-and-drop replace works the same way as Step 2), Vercel auto-detects the commit and redeploys in under a minute. The URL stays the same.

---

## What this deployment actually serves

The dashboard requires internet to load Leaflet (CDN), Esri satellite tiles, and OpenStreetMap streets tiles. These are public free services with no API key required. Bandwidth is fine for any reasonable traffic level.

The data shown on the dashboard is illustrative simulation — labeled as such in the footer. The framework, the cryptographic standards (CJIS, NIST 800-53, NIST 800-207, FIPS 140-3 L3, NIST PQC FIPS 203/204, StateRAMP Moderate), the four-tier access model, the Dunwoody Standard, and the three-phase implementation plan are all real reference architecture. When the cooperative is funded for production, the same dashboard can plug into an actual ledger, real satellite-tile providers with API keys, Atlanta DOT's traffic feed, live ALPR triggers, and a real stablecoin disbursement layer.

Anyone scrutinizing the live deployment will see the demonstration-data note in the footer. That is load-bearing for the project's credibility through the January 2027 renewal window.

Outside The Wire Productions&copy;
