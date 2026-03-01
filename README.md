# Scriptures & Stone

A blog for stories from the Ramayana and Mahabharata.

---

## How to Add a New Story

### Step 1 — Write your story

Create a `.md` file in the `posts/` folder. Name it with hyphens, no spaces:

```
posts/exile-of-the-pandavas.md
posts/hanuman-crosses-the-ocean.md
```

Do NOT add `---` frontmatter at the top. Just start writing directly.

---

### Step 2 — Add one entry to posts.json

Open `posts.json` and add your story:

```json
[
  {
    "file":    "breaking-of-the-great-bow.md",
    "title":   "Breaking of the Great Bow",
    "epic":    "Ramayana",
    "excerpt": "In the court of Janaka...",
    "date":    "March 2026"
  },
  {
    "file":    "exile-of-the-pandavas.md",
    "title":   "Exile of the Pandavas",
    "epic":    "Mahabharata",
    "excerpt": "After the dice game, five brothers walked into the forest...",
    "date":    "April 2026"
  }
]
```

- `epic` must be `"Ramayana"` or `"Mahabharata"` exactly
- Never edit `index.html`

---

### Step 3 — Upload both files to GitHub

GitHub Pages will serve the update immediately.

---

## Markdown Formatting

| What you want     | What to type              |
|-------------------|---------------------------|
| Section heading   | `## Heading`              |
| Verse / quote     | `> Line of verse`         |
| Bold              | `**word**`                |
| Italic            | `*word*`                  |
| Divider line      | `---`                     |

---

## Folder Structure

```
scriptures-and-stone/
├── index.html        ← Never edit this
├── posts.json        ← Only file you edit to add stories
├── README.md
└── posts/
    ├── breaking-of-the-great-bow.md
    └── your-next-story.md
```

---

## GitHub Pages Setup (one time only)

1. Push this folder to a GitHub repository
2. Go to **Settings → Pages**
3. Source: **Branch: main** · Folder: **/ (root)** → Save
4. Live at: `https://yourusername.github.io/repo-name/`

> Note: Stories will NOT load if you open index.html directly from your computer.
> Always view it via GitHub Pages (or run a local server with: `npx serve .`)
