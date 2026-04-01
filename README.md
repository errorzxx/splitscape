# ◈ SplitScape — Smart Group Expense Splitter

> Split without the stress. No login. No chaos. Just settle up.

**SplitScape** is a zero-login, mobile-first web app that takes the friction out of splitting group expenses. Built for the way Indian college students actually travel — spontaneous, informal, and always on WhatsApp.

crafted by **Ali Hussain Khan**

---

## Live Demo

> Deploy the `splitscape.html` file on [Vercel](https://vercel.com) or [Netlify](https://netlify.com) and paste your link here.

---

## Features

- **Zero login** — create a trip and share a 6-character code instantly
- **4 split modes** — Equal, Custom Amount, Percentage, and Exclude-based
- **Debt simplification algorithm** — minimum transactions to settle all balances
- **8 expense categories** — Food, Ride, Stay, Drinks, Entry, Shop, Fun, Other
- **Live balance tracking** — real-time net balance per person, color-coded
- **WhatsApp export** — one-tap ready-to-paste settlement message
- **Stats dashboard** — category breakdown, top payer, per-person fair share
- **Mark as done** — tick off transactions as they get settled
- **Print to PDF** — browser-native print for offline records
- **Mobile responsive** — works perfectly on any phone browser
- **No backend** — everything runs in the browser, zero server needed

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Pure HTML5, CSS3, Vanilla JavaScript |
| Typography | Syne + DM Sans (Google Fonts) |
| Visual Design | Glassmorphism, CSS backdrop-filter, Aurora gradients |
| Animations | Pure CSS keyframes |
| State | In-memory JavaScript objects (session-based) |
| PDF Export | Browser native print API |
| Clipboard | Web Clipboard API |
| Deployment | Single `.html` file — Vercel / Netlify / GitHub Pages |

---

## The Algorithm

SplitScape uses a **Greedy Debt Simplification** algorithm to minimize the number of transactions needed to settle all balances.

### How it works

**Step 1 — Calculate net balance for everyone:**
```
Net Balance = Total Paid − Total Owed
```

**Step 2 — Separate into two lists:**
- Creditors — positive balance (they should receive money)
- Debtors — negative balance (they need to pay)

**Step 3 — Greedy match:**
- Sort both lists by amount, largest first
- Match the biggest debtor with the biggest creditor
- The smaller of the two amounts becomes the transaction
- Reduce both balances and repeat until zero

### Example
```
Ali paid ₹3600 for hotel
Raj paid ₹800  for petrol
Sara paid ₹0

Total = ₹4400 → Each owes ₹1466.67

Net: Ali = +2133, Raj = -666, Sara = -1466

Result:
Sara → Ali  ₹1466
Raj  → Ali  ₹ 666

Only 2 transactions instead of 6
```

This is a known CS problem (Minimum Cash Flow). The greedy approach gives optimal or near-optimal results in **O(n log n)** time.

---

## How to Run

### Option 1 — Open directly (zero setup)

```
Just double-click splitscape.html
It opens in your browser and works immediately.
No installation. No server. No build step.
```

### Option 2 — Local server (for development)

```bash
# Python (built into most systems)
python -m http.server 3000
# Open: http://localhost:3000/splitscape.html

# OR using Node.js
npx serve .
```

### Option 3 — GitHub Pages (free, permanent link)

```
1. Create a new GitHub repository
2. Upload splitscape.html → rename it to index.html
3. Go to Settings → Pages → Source → main branch → / (root)
4. Live at: https://yourusername.github.io/splitscape
```

### Option 4 — Netlify (easiest, 10 seconds)

```
1. Go to netlify.com and log in
2. Drag and drop splitscape.html onto the dashboard
3. Done — you get a live URL instantly
```

### Option 5 — Vercel

```bash
npm install -g vercel
vercel
# Follow the prompts — live URL in under a minute
```

---

## Project Structure

```
splitscape/
└── splitscape.html    ← entire app: HTML + CSS + JS in one file
```

One file. No dependencies. No node_modules. No build step.

---

## Demo Script (for judges — under 3 minutes)

```
1. Open app → type "Goa Trip 2026" → Create
2. Add 4 friends: Ali, Sara, Raj, Priya → Start Splitting
3. Add: Hotel ₹3600 → Ali paid → Equal split
4. Add: Petrol ₹800 → Raj paid → Ride category
5. Add: Beach dinner ₹1200 → Sara paid → Exclude Priya
6. Balances tab → show live net amounts
7. Settle Up → show minimum transactions
8. WhatsApp button → show the ready-to-send message
9. Stats tab → show category breakdown chart
```

---

## Hack-A-Sprint 2026 Bonus Checklist

- [x] No login required — instant access
- [x] Mobile responsive — works on any phone browser
- [x] Single file — deployable on Netlify in 10 seconds
- [x] Open GitHub repo with README
- [ ] Live public URL ← add after deployment

---

## License

MIT — free to use, modify, and deploy.

---

<div align="center">
  <strong>◈ SplitScape</strong> — crafted by RAGNAROk
</div>
