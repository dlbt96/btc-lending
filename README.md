# ₿ Collateral Protocol (btc-lending)

A **real-time, multiplayer DeFi lending classroom game** where students can:
- **Lend** USD against BTC collateral
- **Borrow** USD to lever into BTC
- **Trade BTC** as the teacher moves the price day-by-day
- Build “reputation / access” via a **τ-credit** system (repay loans to unlock undercollateralized credit)

The whole app is currently a **single-page web app** in `index.html`.

---

## Gameplay overview

### Roles
- **Teacher (Host):** creates a room, sets initial parameters, advances time (“Day”), and can move BTC price.
- **Students:** join the room, then lend/borrow/trade and manage risk.

### Core mechanics
- **Lend:** publish a lending offer; other players request loans; you approve/reject.
- **Borrow:** borrow cash → buy BTC → post collateral → borrow more (leveraged loop).
- **BTC Trade:** buy/sell BTC at the current teacher-controlled price.
- **τ-credit:** after **τ repaid loans**, players unlock “undercollateral” credit (UI describes “100% LTV, no liquidation”).
- **Risk:** leverage amplifies losses and can cascade into defaults.

---

## Room settings (Teacher)

In the lobby, the teacher can set:
- Starting Cash (USD)
- Starting BTC
- BTC Start Price
- **τ threshold**
- Auto-clock speed (sec/day, 0 = off)

During the game, the teacher dashboard supports:
- Next Day / Auto
- Quick price moves (±10%, ±25%)
- Stats: active loans, defaults vs repaid, BTC traded, event log

---

## Player actions

### Publish a lending offer
Players can set:
- Interest Rate (% APR)
- Max LTV (%)
- Max Loan Size (USD)
- Minimum τ-credit required

### Post a borrow request
Borrowers can set:
- Amount (USD)
- Max rate (% APR)
- Duration (7/14/30/60/90 days)

### Loan lifecycle
- Borrower sends request
- Lender fulfills (chooses rate + LTV)
- Borrower repays (or defaults)
- Stats update in dashboard & player panel

---

## Run locally

Because this is a single HTML file, you can run it with any static server. Simply double click index.html to run.
