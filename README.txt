HYPE — Birthday Edition for Okechukwu Ugoji
===========================================

A standalone, fully-tailored birthday version of the HYPE party app.
Completely separate from your main HYPE app.

-----------------------------------------------------------------
WHAT'S SPECIAL IN THIS VERSION
-----------------------------------------------------------------
  - Opening splash: his PHOTO (gold-framed) + "Happy Birthday, Okechukwu Ugoji!"
    with the message "Happy Birthday to you from all of us."
  - "Celebrating Okechukwu Ugoji today!" banner on the home screen.
  - Birthday mode is ALWAYS on (no date logic needed).
  - ALL premium packs are UNLOCKED FREE (party gift) — every game, every pack.
  - "🧠 Know Okechukwu?" — a standalone game (its own tile) with a custom round
    about him (his role: Group Head, SME Banking; his catchphrases; etc.).
  - "💌 Birthday Wishes" wall — guests post messages that appear LIVE for everyone,
    plus a big-screen TV/projector view.

-----------------------------------------------------------------
THE GAMES (all unlocked)
-----------------------------------------------------------------
  Play on one phone:
    🤳 Charades (act / dance / describe) · 🔥 Truth or Dare · 👑 Most Likely To
    🐺 Werewolf · 🕵️ Spyfall · 🤔 Would You Rather · 🤥 Two Truths & a Lie
    🧠 Trivia Showdown · 🚫 Taboo
    (Werewolf, Spyfall, Taboo and Two Truths each have a "❓ How to play" button.)

  Trivia categories (13):
    🎂 (standalone) Know Okechukwu?  ·  🗺️ Countries  ·  🏦 Nigerian Banks
    📖 Nigeria History  ·  🏛️ Nigerian Politics  ·  💰 Nigerian Economy
    🎶 Naija Music  ·  🎧 International Music  ·  📜 World History
    🌍 General  ·  🇳🇬 Naija  ·  ⚽ Sports  ·  🎬 Movies  ·  🔬 Science

  Play ONLINE (everyone on their own phone, join by code/QR):
    🐺 Werewolf  ·  🕵️ Spyfall  ·  🧠 Live Trivia  ·  🤔 Would You Rather  ·  👑 Most Likely To
    (Open 📡 Online Rooms -> pick the game -> Create -> share the code or QR.)

-----------------------------------------------------------------
FILES TO UPLOAD (both go in the same repo)
-----------------------------------------------------------------
  index.html   - the app
  oke.png      - his photo (the splash loads this by name, so it MUST be uploaded too)

-----------------------------------------------------------------
HOW TO PUT IT ONLINE (own link, ~3 min)
-----------------------------------------------------------------
  1) GitHub -> New repository -> name: hype-birthday -> Public -> Create.
  2) Add file -> Upload files -> drag in BOTH index.html AND oke.png -> Commit.
  3) Settings -> Pages -> Deploy from branch: main / root -> Save.
  4) Live at: https://chimmysmallz.github.io/hype-birthday/  -> share this link.

-----------------------------------------------------------------
ONE FIREBASE STEP (needed for Wishes Wall + online games)
-----------------------------------------------------------------
  In Firebase -> Realtime Database -> Rules, use this and click Publish:

  {
    "rules": {
      "rooms":        { "$code": { ".read": true, ".write": true } },
      "entitlements": { ".read": true, "$id": { ".write": false } },
      "wishes":       { ".read": true, ".write": true }
    }
  }

  (The "wishes" line lets guests post birthday messages. "rooms" powers all the
  online games. Uses the same Firebase as your main app, so it works right away.)

-----------------------------------------------------------------
THREE PARTY LINKS TO SHARE
-----------------------------------------------------------------
  Everyone plays:        https://chimmysmallz.github.io/hype-birthday/
  TV / projector wall:   https://chimmysmallz.github.io/hype-birthday/?wall=1
  Post a wish (QR goal): https://chimmysmallz.github.io/hype-birthday/?wish=1

  The big-screen wall (?wall=1) shows a full-screen, auto-scrolling live feed of
  everyone's wishes, his photo up top, and a QR guests scan to add their own.
  (You can also open it in-app: 💌 Birthday Wishes -> "📺 Big-screen view".)

-----------------------------------------------------------------
FOR 20 GUESTS — QUICK TIPS
-----------------------------------------------------------------
  - Use ONLINE rooms so everyone plays on their own phone.
  - 🐺 Werewolf and 🧠 Live Trivia are the best crowd games for a big group.
  - 🕵️ Spyfall plays best in smaller clusters (4-8) — split into 2-3 rooms for 20.
  - Firebase free tier allows 100 live connections, so 20 is well within limits.

-----------------------------------------------------------------
NOTES
-----------------------------------------------------------------
  - Online games are real-time; test on a couple of phones once uploaded.
  - After the party, just delete this repo — your main app is untouched.
