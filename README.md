# 🎴 PAM's Birthday Duel

A Yu-Gi-Oh–style birthday card game for PAM, from **Gautier** & **Marine**.

Beat Gautier in a short (rigged-to-win) duel → unlock 3 delivered meals
(Chinese 🥡 / Korean 🍲 / Japanese 🍣). Tapping a meal notifies Gautier and
marks it as used.

It's **one self-contained file** (`index.html`) — no build step, no backend.

---

## ▶️ Try it right now

Just open `pam-birthday/index.html` in any browser (double-click it). Everything
works locally, including "used meals" memory (browser `localStorage`).

---

## ✉️ The meal email — two modes (no setup required to work)

When PAM redeems a meal, the app notifies **moulingautier@gmail.com**:

1. **Auto-send (recommended)** — silent email, no action from PAM.
   - Go to <https://web3forms.com>, enter `moulingautier@gmail.com`, get a free
     **Access Key** (takes ~1 min, confirm via the email they send you).
   - Open `index.html`, find the `CONFIG` block near the top of the `<script>`,
     and paste the key:
     ```js
     web3formsKey: "your-access-key-here"
     ```
2. **Fallback (works out of the box)** — if no key is set, tapping a meal opens
   PAM's email app with a pre-filled message to you that he taps **Send** on.

Either way the meal is marked **Used** so it can't be redeemed twice.

> Change the recipient by editing `CONFIG.notifyEmail`.

---

## 🌐 Hosting it online

### Option A — Drag & drop (fastest)
Drop `index.html` onto **Netlify Drop** (<https://app.netlify.com/drop>) or import
the repo into **Vercel**. Instant public URL.

### Option B — GitHub Pages (included workflow)
This folder ships with `.github/workflows/pam-birthday-pages.yml`, which deploys
`pam-birthday/` to GitHub Pages.

1. In the repo: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
2. Push to this branch (already wired) — the action publishes the page.
3. Your URL: `https://<owner>.github.io/<repo>/`

> Note: a repo can only host one GitHub Pages site. If this repo already uses
> Pages for something else, prefer Option A or a dedicated repo.

---

## 🎮 Tweaks
All in `index.html`:
- **Duel difficulty / length** — edit the `MARINE` / `FOE1` / `FOE2` stats and the
  `attack()` flow. It's intentionally scripted so PAM always wins quickly.
- **Meals** — edit the `MEALS` array (emoji, title, description).
- **Art** — emoji placeholders today; swap the `.art` / `.mart` blocks for
  AI-generated images later (`<img src="...">`).
