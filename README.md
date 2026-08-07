# Web-RTC-Poker
</====================================3
# ♠️ Poker by Rice

A lightweight, serverless, peer-to-peer (P2P) Texas Hold'em poker web application built with vanilla HTML, CSS, and JavaScript. Powered by **WebRTC DataChannels**, players can connect directly with each other without relying on a central database or game server.

---

## ✨ Features

- **Direct P2P Connectivity:** Establish browser-to-browser connections using WebRTC offer/answer signaling tokens.
- **Dynamic Betting Engine:** Full Texas Hold'em game loop supporting Small/Big Blinds, dynamic state transitions (`[Check]`, `[Call]`, `[Bet]`, `[Raise]`, `[Fold]`), and live bet tracking.
- **Interactive Chip Denominations:** Selectable color-coded chip values ($5, $10, $25, $100) for custom raise and bet sizing.
- **Customizable UI Themes:** Built-in theme selector (Indigo Slate, Cyber Neon, Nordic Frost) and card text scaling for custom visual preferences.
- **Zero Dependencies:** Fully self-contained single-file HTML application—no build step or `npm install` required.

---

## 🚀 How to Play (Step-by-Step)

Since this game uses WebRTC, two players must perform a manual token handshake to connect.

### Step 1: Open the Application
Both players open `poker game.html` in their web browser (or via GitHub Pages / local server).

### Step 2: Establish the WebRTC Handshake

1. **Player 1 (Host):**
   - Click **"Host Table"**.
   - Copy the generated token string inside **"Your Token Signature"**.
   - Send this offer token code to Player 2 (via Discord, Slack, email, etc.).

2. **Player 2 (Joiner):**
   - Click **"Join Table"**.
   - Paste Player 1's token string into **"Counterpart Peer Token"**.
   - Copy the newly generated token inside **"Your Token Signature"** and send it back to Player 1.

3. **Player 1 (Host Finish):**
   - Paste Player 2's answer token into **"Counterpart Peer Token"**.
   - Click **"Initialize Handshake"**.

Once connected, the lobby setup screen automatically disappears and reveals the poker table!

---

## 🎮 Game Controls

- **Automatic Blinds:** A Small Blind ($5) and Big Blind ($10) are automatically deducted and rotated between players each hand.
- **Selecting Chips:** Click on any colored poker chip in the tray ($5, $10, $25, $100) to adjust your bet/raise size before taking an aggressive action.
- **Actions:**
  - **Check / Call:** Pass the turn or match your opponent's bet.
  - **Bet / Raise:** Place chips into the active pot using your selected chip value.
  - **Fold:** Surrender the current hand and award the pot to your opponent.
- **Dealing Next Phase:** The host clicks **"Next Phase"** after bets are equalized to advance from Preflop ➔ Flop ➔ Turn ➔ River ➔ Showdown.

---

## ⚙️ Visual Settings

Click the **gear icon (⚙️)** in the top right corner to open the UI Preferences panel:
- **Theme Colorway:** Switch between *Indigo Slate*, *Cyber Neon*, and *Nordic Frost*.
- **Card Text Scale:** Toggle *Accessibility Plus* for enlarged card rank visibility.

---

## 🛠️ Built With

- **HTML5 & CSS3** (Flexbox, CSS Grid, CSS Variables)
- **Vanilla JavaScript (ES6+)**
- **WebRTC API** (`RTCPeerConnection` & `RTCDataChannel`)
