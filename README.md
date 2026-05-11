# ⚡ IronWake Docs — Trello Power-Up

A living Markdown document editor embedded directly inside your Trello cards.
Built for Project: IronWake.

---

## Features

- **Full Markdown editor** inside every card (bold, italic, headings, lists, checkboxes, tables, code blocks)
- **Live preview + split view** — toggle between Edit / Split / Preview modes
- **Auto-save** — saves to Trello's card data storage after 1.8s of inactivity
- **Manual save** — Ctrl+S / ⌘+S
- **Toolbar** — one-click formatting buttons
- **Word + character count**
- **IronWake dark theme** — matches your board aesthetic

---

## Setup (5 steps)

### 1. Get a Trello API Key
Go to → https://trello.com/power-ups/admin
- Click **"New Power-Up"**
- Fill in: Name = `IronWake Docs`, Iframe connector URL = your hosted URL (see step 3)
- Copy your **API Key**

### 2. Add your API Key
In both `index.html` and `card-back.html`, replace:
```
YOUR_TRELLO_API_KEY
```
with your actual key.

### 3. Host the files (free options)

**Option A — GitHub Pages (recommended)**
1. Push this folder to a GitHub repo
2. Go to repo Settings → Pages → Source: main branch / root
3. Your URL will be: `https://yourusername.github.io/ironwake-powerup/`

**Option B — Netlify Drop**
1. Go to https://app.netlify.com/drop
2. Drag and drop this entire folder
3. Copy the generated URL

### 4. Register the Power-Up
Back in https://trello.com/power-ups/admin:
- Set **Iframe connector URL** to: `https://your-url/index.html`
- Capabilities: check `card-buttons` and `card-back-section`
- Save

### 5. Enable on your board
- Open your **Project: IronWake** Trello board
- Click **Power-Ups** → search for `IronWake Docs` (under "Custom" or your workspace)
- Click **Add**

---

## Usage

Once enabled, every card gets:
- A **"Living Doc"** button at the top of the card
- A **"📄 IronWake Docs"** section at the bottom of every card back

Click either to open the embedded Markdown editor.

### Keyboard Shortcuts
| Shortcut | Action |
|----------|--------|
| Ctrl/⌘ + S | Save |
| Ctrl/⌘ + B | Bold |
| Ctrl/⌘ + I | Italic |
| Tab | Insert 2 spaces |

---

## File Structure

```
ironwake-powerup/
├── index.html        ← Power-Up connector (Trello loads this)
├── card-back.html    ← The Markdown editor UI
└── README.md         ← This file
```

---

## Data Storage

Content is stored using Trello's built-in Power-Up storage API (`t.set / t.get`).
Each card stores its own Markdown content under the key `ironwake-doc-content`.
Data is scoped to the card and shared across all board members.
No external database needed.

