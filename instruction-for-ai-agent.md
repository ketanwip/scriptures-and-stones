# Instructions for AI Agent: Daily Story Generation

## Project Overview
**Location:** `/Users/ketansolanki/Documents/scriptures-and-stones`  
**Purpose:** Generate one story daily from Hindu scriptures (Ramayana, Mahabharata, Puranas, Vedas) at 2:00 PM EST

---

## Daily Workflow (Every Day at 2 PM)

**Complete workflow**: Pick topic → Generate story → Save file → Update JSON → Git commit/push/PR/merge → Verify

**Fully automated** — no manual intervention required. Story goes live in main branch automatically.

### Step 1: Pick a Topic
- Read `/Users/ketansolanki/Documents/scriptures-and-stones/future-stories.md`
- Read `/Users/ketansolanki/Documents/scriptures-and-stones/posts.json`
- **Select ONE topic** from `future-stories.md` that has NOT been used yet (check against existing entries in `posts.json`)
- **Avoid duplicates**: Cross-reference topic titles with existing story titles/files

### Step 2: Generate the Story
- Read `/Users/ketansolanki/Documents/scriptures-and-stones/prompt.md` for style guidelines
- Follow the three-factor blend:
  1. **Bibek Debroy Factor**: Scriptural authenticity, oldest versions, deep lore about artifacts/lineages
  2. **Michael Crichton Factor**: Technical detail, spiritual science, sensory precision
  3. **Dan Brown Factor**: High-stakes hook, flowing narrative (no sub-headings), pivot point focus
- **Key constraints**:
  - Medium-sized narrative (aim for ~4000-5500 characters based on existing examples)
  - Use Markdown for emphasis
  - No bullet points or sub-headings in the story itself
  - Authentic, respectful, yet gritty tone
  - Source from traditional texts only

### Step 3: Create the Story File
- Create filename: Use kebab-case (lowercase with hyphens), descriptive
  - Example: `breaking-of-the-great-bow.md`, `drona-lesson-on-focus.md`
- Save in: `/Users/ketansolanki/Documents/scriptures-and-stones/posts/[filename].md`
- File should contain ONLY the story text (no metadata header)

### Step 4: Update posts.json
- Location: `/Users/ketansolanki/Documents/scriptures-and-stones/posts.json`
- Add new entry to the JSON array with:
  ```json
  {
    "file": "filename.md",
    "title": "Story Title",
    "epic": "Ramayana|Mahabharata|Puranas",
    "excerpt": "First compelling sentence or hook from the story (40-60 words)",
    "date": "Month YYYY"
  }
  ```
- Maintain proper JSON formatting (commas, brackets)
- Use current month and year for date

### Step 5: Git Workflow
**IMPORTANT**: This project is version-controlled. After generating the story:

1. **Navigate to project directory**:
   ```bash
   cd /Users/ketansolanki/Documents/scriptures-and-stones
   ```

2. **Create a new branch**:
   ```bash
   git checkout -b story/YYYY-MM-DD-topic-name
   ```
   - Use current date and kebab-case topic name

3. **Stage changes**:
   ```bash
   git add posts/[filename].md posts.json
   ```

4. **Commit with descriptive message**:
   ```bash
   git commit -m "Add story: [Story Title]"
   ```

5. **Push branch**:
   ```bash
   git push -u origin story/YYYY-MM-DD-topic-name
   ```

6. **Create Pull Request**:
   ```bash
   gh pr create --title "Add story: [Story Title]" --body "Daily scripture story generated on [date]" --base main
   ```

7. **Merge the PR**:
   ```bash
   gh pr merge --merge --delete-branch
   ```
   - Merges immediately (story is already quality-checked)
   - Deletes the feature branch automatically

### Step 6: Verify
- Confirm file created in `posts/` folder
- Confirm `posts.json` updated and valid JSON
- Mark topic as "used" mentally (it's now in posts.json)

---

## File Structure Reference
```
scriptures-and-stones/
├── prompt.md              # Story style guidelines
├── future-stories.md      # Topic bank (pick from here)
├── posts.json             # Story index (update after each story)
└── posts/
    ├── story-1.md
    ├── story-2.md
    └── story-N.md
```

---

## Quality Checklist
- [ ] Topic is unique (not in posts.json)
- [ ] Story follows all three style factors (Debroy + Crichton + Brown)
- [ ] Story is flowing narrative (no sub-headings)
- [ ] Technical/historical detail included
- [ ] High-stakes hook at beginning
- [ ] Filename is kebab-case
- [ ] posts.json updated with proper structure
- [ ] JSON is valid (no syntax errors)
- [ ] New branch created with proper naming
- [ ] Files committed with descriptive message
- [ ] Branch pushed to remote
- [ ] Pull Request created to merge into main
- [ ] PR merged successfully
- [ ] Feature branch deleted
- [ ] Story now live in main branch

---

## Automation Setup
**Cron Job**: Daily at 2:00 PM EST
- Session: `isolated` (so it doesn't clutter main chat)
- Model: Can use `haiku` or `sonnet` depending on quality needs
- Task: Execute all 5 steps above
- Delivery: Optionally announce completion to main session

---

## Notes
- There are ~80 topics in `future-stories.md` — enough for almost 3 months of daily stories
- When running low on topics (<10 remaining), alert Ketan to add more
- If a topic seems too similar to an existing story, skip and pick the next one
- Prioritize variety: alternate between Ramayana/Mahabharata/Puranas epics
