# Brain Snack Quiz

> *Because apparently you forgot. Again.*

A cozy, self-contained quiz app that lives entirely in a single HTML file. No server, no install, no account — just open it and start studying.

---

## What is this?

Brain Snack is a personal flashcard-style quiz tool built for people who actually want to review things, not just collect notes. You write the questions, you take the quiz, you see where you're weak. That's it.

It was built for students, self-learners, and anyone who has a stack of content they need to actually internalize rather than passively read.

---

## Features

- **Three question types** — Multiple choice (MCQ), True/False, and Multi-select
- **Rich question editor** — Write questions with Markdown, math equations (via KaTeX), code blocks with syntax highlighting, and embedded images
- **Smart shuffle** — Questions and answer choices are randomized on every retake
- **Per-question feedback** — Submit each answer individually and get instant correct/incorrect feedback with explanations
- **Review mode** — After finishing, toggle "Mistakes Only" to focus on what you got wrong
- **Progress tracking** — The app remembers your last attempt score per exam
- **Import / Export** — Back up your entire question database as a JSON file and restore it anywhere
- **Dark mode** — Because studying at 2am is a personality trait
- **Fully offline** — No internet required after the initial page load (except for Google Fonts and math rendering libraries)

---

## How to use it

### As a student

1. Open `index.html` in any modern browser
2. Click any exam card on the **Menu** page to start a quiz
3. Answer each question and hit **Check** to see if you're right
4. When you're done, click **End Exam** to see your score
5. Use the **Review Mistakes Only** toggle to drill the ones you got wrong
6. Click **Retake Shuffled** to go again with everything randomized

### As a content creator / teacher

1. Go to **Chef** (the Admin panel) in the top nav
2. Under **Manage Structure**, create a Subject and then an Exam inside it
3. Under **Create Question**, select your exam and start writing questions
   - Use the toolbar to insert bold/italic text, code blocks, math equations, or images
   - Mark which answer(s) are correct
   - Add an explanation that shows after the student answers
4. Use **Modify & Delete Questions** to edit or remove anything
5. Go to **Fridge** (Backup) to export your database as a JSON file — keep this safe, it's your content

### Sharing with others

Host the file on GitHub Pages (free) and share the link. Each visitor gets their own isolated progress stored in their browser's local storage — they won't see your data and you won't see theirs.

---

## Technical details

Built with zero dependencies you need to install. Everything is embedded in one HTML file.

| Thing | How |
|---|---|
| Markdown rendering | [marked.js](https://cdnjs.cloudflare.com/ajax/libs/marked/9.1.6/marked.min.js) via CDN |
| Math equations | [KaTeX](https://katex.org/) via CDN |
| Fonts | Quicksand + Space Mono via Google Fonts |
| Data storage | Browser `localStorage` |
| Portability | JSON export/import |

The database schema is straightforward — subjects contain exams, exams contain questions. Everything is stored under the key `quizforge_db` in localStorage.

---

## Important notes

- **Your data lives in your browser.** Clearing browser data or private/incognito mode will wipe it. Export your JSON regularly if you care about your questions.
- **Images are embedded as base64.** This keeps the file self-contained but can make your exported JSON large if you use many images. Keep images under 1.5MB each.
- **Math syntax** uses `$...$` for inline and `$$...$$` for block equations. The equation builder in the toolbar handles this for you.

---

## License

Do whatever you want with it. It's one HTML file.
