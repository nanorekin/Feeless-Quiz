# Feeless Quiz

A free, single-file browser crypto trivia game with Nano at its heart. 80 questions on Nano, Bitcoin, Ethereum, other coins, key ideas, security and crypto history, each with a short explanation. No build step, no backend, no fees.

## Play

- **Daily quiz:** 10 questions, the same for everyone, new every day at 00:00 UTC. Finish it to keep your daily streak.
- **Quick 10:** a fresh random round of 10 questions.
- **Survival:** keep answering until you have made 3 mistakes.
- **Timer and scoring:** 15 seconds per question. A correct answer is worth 100 points, plus up to 50 for speed and up to 50 for your streak.
- **50/50:** removes two wrong answers once per round (supporters get two).
- **Keyboard:** press 1 to 4 to answer, Enter or Space for the next question.
- **Ranks:** Newbie, Hodler (25 correct answers), Diamond Hands (100), Whale (250), Satoshi (500).
- **Sharing:** a Wordle-style grid of green and red squares.

Everything is stored in the player's browser. Questions are for fun and learning and are not financial advice.

## Adding or editing questions

Questions live in the `POOL` array near the top of the script in `index.html`, in this format. The correct answer is always listed first; the game shuffles the order:

```
["Category", "Question?", ["Correct answer", "Wrong 1", "Wrong 2", "Wrong 3"], "Short explanation."],
```

## Deploy on GitHub Pages

1. Create a new repository, for example `feeless-quiz`.
2. Upload `index.html` and `README.md` to the root of the repository.
3. Open **Settings > Pages**, set the source to **Deploy from a branch**, choose `main` and `/ (root)`, then save.
4. After a minute the game is live at `https://<your-username>.github.io/feeless-quiz/`.

## Donations

The tip card works the same way as in the other Feeless games:

- A `nano:` payment link with the chosen amount, shown as a QR code and an **Open in wallet** button.
- A **Copy address** button.
- An **I've sent it, check** button that asks public Nano nodes whether a matching payment arrived, and unlocks the supporter perks (Gold, Mint and Neon accent colours, and a second 50/50 per round) on that browser.

To use a different wallet, change `NANO_ADDRESS` near the top of the script in `index.html`. If the public RPC endpoints in `RPCS` ever block browser requests, point them at your own proxy.

The supporter unlock is stored in `localStorage`, so it is a thank-you perk, not secure access control.

Add `?selftest` to the URL to expose a small `window.__wq` object for automated tests.
