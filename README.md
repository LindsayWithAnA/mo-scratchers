# 🎰 MO Scratcher Tracker

A mobile-first progressive web app (PWA) that shows the **top 5 Missouri Lottery scratcher games with the best current odds** — refreshed on demand using live data from molottery.com — plus a personal wins tracker to log your results and monitor your real ROI.

> Built for personal use. Designed to work as a home screen app on iPhone via Safari.

---

## Features

- **Live Odds Refresh** — Tap one button to pull current average odds for all active MO Lottery scratchers, ranked best to worst. Powered by Claude AI with real-time web search.
- **Top 5 Display** — Shows game name, game number, ticket price, average odds, top prize, and active/NLD status at a glance.
- **Wins Tracker** — Log every ticket purchase: game name, price, quantity, and amount won. All data stays on your device.
- **P&L Dashboard** — Running totals for amount spent, amount won, net profit/loss, and ROI percentage.
- **Spend Chart** — Visual breakdown of your spending and returns by ticket price tier.
- **PWA Ready** — Add to iPhone home screen via Safari for a true app-like experience with no App Store required.

---

## How It Works

When you tap **Refresh Odds**, the app calls the [Anthropic API](https://www.anthropic.com) using your personal API key. Claude performs a live web search of [molottery.com](https://www.molottery.com), reads the current "Average Chances" odds from each active game's detail page, and returns the top 5 ranked by best (lowest) odds.

Cached results are stored locally so the last fetch is always visible — even offline — until you refresh again.

---

## Setup

### 1. Get an Anthropic API Key

1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Sign in and navigate to **API Keys**
3. Click **Create Key** — name it something like `MO Scratchers App`
4. **Copy the key immediately** — it is only shown once
5. Add a payment method under **Billing** (usage is typically ~$0.02–0.05 per refresh)

### 2. Deploy to GitHub Pages

1. Create a new **public** repository on GitHub (e.g. `mo-scratchers`)
2. Upload `index.html` from this repo *(the main app file)*
3. Go to **Settings → Pages → Source → Deploy from a branch**
4. Select **main** branch, root folder, and click **Save**
5. Your app will be live at:
   ```
   https://yourusername.github.io/mo-scratchers
   ```

### 3. Add to iPhone Home Screen

1. Open your GitHub Pages URL in **Safari** on your iPhone
2. Tap the **Share** button (box with arrow)
3. Scroll down and tap **Add to Home Screen**
4. Tap **Add** — the app icon will appear on your home screen

### 4. Enter Your API Key in the App

1. Open the app and tap the **⚙️ Setup** tab
2. Paste your Anthropic API key
3. Tap **Test Connection** to confirm it's working
4. Head to **📊 Top 5 Odds** and tap **⚡ Refresh**

---

## Data & Privacy

| What | Where it lives |
|---|---|
| Anthropic API key | Your device only (localStorage) |
| Cached odds data | Your device only (localStorage) |
| Win/loss history | Your device only (localStorage) |
| Data sent externally | Only to `api.anthropic.com` when you tap Refresh |

No accounts, no servers, no tracking. This is a single HTML file.

---

## Odds Explained

The **Average Chances** figure (e.g. "1 in 2.64") comes directly from each game's official detail page on molottery.com. It represents the overall probability of winning **any prize** on a given ticket — including the minimum prize tier.

**Lower number = better odds.** A game with odds of 1 in 2.64 means roughly 38% of tickets win something, compared to 1 in 4.84 where only about 21% do.

> ⚠️ Better odds of winning *something* does not guarantee profitability. All lottery games are designed so the house retains a percentage of total ticket sales. This app is for informational and entertainment purposes only.

---

## Cost Estimate

Each tap of **Refresh Odds** makes one API call using Claude with web search.

| Usage | Estimated cost |
|---|---|
| 1 refresh | ~$0.02–0.05 |
| 20 refreshes/month | ~$0.40–$1.00 |
| 100 refreshes/month | ~$2.00–$5.00 |

New Anthropic accounts receive a small free credit to get started.

---

## Tech Stack

- Vanilla HTML / CSS / JavaScript — zero dependencies, zero build steps
- [Anthropic Messages API](https://docs.anthropic.com) with `web_search` tool
- `localStorage` for all persistence
- PWA via Safari "Add to Home Screen" (no service worker required for basic functionality)

---

## Help & Support

This is a personal project, but if something isn't working here are the best places to troubleshoot:

| Issue | Where to go |
|---|---|
| API key not working / Test Connection fails | [console.anthropic.com](https://console.anthropic.com) — verify your key is active and billing is set up |
| Odds not loading / refresh errors | Check your internet connection; Anthropic API status at [status.anthropic.com](https://status.anthropic.com) |
| API usage & billing questions | [Anthropic Support](https://support.anthropic.com) |
| MO Lottery data looks wrong | Verify directly at [molottery.com](https://www.molottery.com/scratchers-list.do) |
| GitHub Pages not loading | [GitHub Pages docs](https://docs.github.com/en/pages) or [GitHub Community](https://github.com/orgs/community/discussions) |
| Bug reports or suggestions | Open an [Issue](../../issues) on this repository |

---

## License

Personal use only. Not affiliated with or endorsed by the Missouri Lottery Commission or Anthropic.

---

## Maintainer

[@LindsayWithAnA](https://github.com/LindsayWithAnA)

---

*Built in March 2026 with Claude Sonnet.*
