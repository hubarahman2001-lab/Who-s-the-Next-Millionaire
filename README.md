# Who's the Next Millionaire

A self-contained, browser-based quiz game styled after *Who Wants to Be a Millionaire*, built as a single `index.html` file with no build step and no dependencies to install. Drop it in a repo, turn on GitHub Pages, and embed it on your college site with an iframe.

## What's included

- `index.html` — the entire game: markup, styling, and logic in one file.
- 15 placeholder general-knowledge questions with a $100 → $1,000,000 prize ladder and safe havens at question 5 ($1,000) and question 10 ($32,000).
- Three lifelines: 50:50, Ask the Audience, Phone a Friend.
- A Walk Away option once at least one question has been answered correctly.

## 1. Put it on GitHub

```bash
git init
git add index.html README.md
git commit -m "Add Who's the Next Millionaire game"
git branch -M main
git remote add origin https://github.com/YOUR-ORG/YOUR-REPO.git
git push -u origin main
```

(Or use GitHub's "upload files" button in the web UI if you'd rather not use the command line.)

## 2. Turn on GitHub Pages

1. In the repo, go to **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to "Deploy from a branch".
3. Set **Branch** to `main` and folder to `/ (root)`, then **Save**.
4. GitHub will publish the site at:
   `https://YOUR-ORG.github.io/YOUR-REPO/`
   (This can take a minute or two the first time.)

## 3. Embed it on your website

Once the Pages URL is live, embed it with an iframe wherever your site allows custom HTML:

```html
<iframe
  src="https://YOUR-ORG.github.io/YOUR-REPO/"
  width="100%"
  height="720"
  style="border:none; border-radius:12px;"
  title="Who's the Next Millionaire">
</iframe>
```

Adjust `height` to taste — around 700–780px keeps the whole game visible without scrolling on most screens. The game itself is responsive down to mobile widths.

## Customizing the questions

Open `index.html` and find the `QUESTIONS` array near the top of the `<script>` block. Each entry looks like:

```js
{ text:"Which planet is known as the Red Planet?", options:["Venus","Mars","Jupiter","Saturn"], correct:1 }
```

- `text` — the question.
- `options` — exactly four answer choices.
- `correct` — the index (0–3) of the correct option.

Replace all 15 with your own content — course trivia, campus history, orientation facts, whatever fits. Keep the easier ones near the top and the hardest near the bottom, since the prize ladder assumes increasing difficulty. The `PRIZES` and `SAFE_HAVENS` arrays just above `QUESTIONS`'s usage in the game logic can also be adjusted if you want different dollar amounts or safe-haven positions.

No rebuild or compile step is needed — just edit and push; GitHub Pages redeploys automatically.
