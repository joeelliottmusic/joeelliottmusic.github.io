# Joe Elliott — Website Guide

Live site: **https://joeelliottmusic.github.io**

This guide explains everything you need to update the website,
even if you've never coded before.

---

## What you need installed

- **Git** — for sending changes to the live site
- **VS Code** — the app you edit the website in
- The website folder, which lives at:
  `/Users/joeelliott/Desktop/website/joeelliottmusic.github.io`

---

## Opening the website folder in Terminal

Terminal is the black command-line app on your Mac (search for it
in Spotlight with Cmd+Space).

Every time you want to work on the website, open Terminal and run:

```bash
cd /Users/joeelliott/Desktop/website/joeelliottmusic.github.io
```

You only need to do this once per session. You'll know it worked
because the line in Terminal will show the folder name.

---

## Before you start editing — pull first

If anyone else (e.g. Eleanor) might have made changes since you
last worked on the site, run this first to download the latest version:

```bash
git pull
```

If it says "Already up to date" that's fine, carry on.

---

## Making changes to the site

The entire website lives in one file: **index.html**

Open it in VS Code (File → Open, navigate to the folder above).
You can edit text directly — for example changing the bio,
updating gig dates, swapping a link.

To update photos, drop the new photo into the same folder as
`index.html` and make sure it's named `hero.jpg` or `hero2.jpg`.

---

## Sending your changes live (push)

Once you've saved your edits in VS Code, go back to Terminal and run
these three commands in order:

```bash
git add .
```
```bash
git commit -m "describe what you changed"
```
```bash
git push
```

For example:
```bash
git commit -m "updated bio and added new photo"
```

After pushing, wait about one minute then refresh the live site
to see your changes.

---

## The full routine from scratch

```
1. Open Terminal
2. cd /Users/joeelliott/Desktop/website/joeelliottmusic.github.io
3. git pull
4. Make your edits in VS Code and save
5. git add .
6. git commit -m "what I changed"
7. git push
8. Wait 1 minute, check the live site
```

---

## Asking Claude Code to make changes for you

For anything more than simple text edits — layout changes, new
sections, styling — use Claude Code inside VS Code. This is the
recommended way to make bigger changes without needing to understand
the code yourself.

**How to open Claude Code:**

1. Open VS Code
2. Open the website folder: File → Open Folder →
   `/Users/joeelliott/Desktop/website/joeelliottmusic.github.io`
3. Click the **Spark icon (⚡)** in the left sidebar

**How to ask for changes:**

Just describe what you want in plain English. Some examples:

> "Add a new section below the bio with a list of upcoming gig dates"

> "Make the name bigger on mobile"

> "Change the gold colour to something slightly warmer"

> "Add a SoundCloud embed below the photo"

> "Make the second photo slightly smaller"

Claude Code will show you a preview of what it wants to change
before applying it. Review it, then accept.

Once you're happy with the result, go to Terminal and push as normal:

```bash
git add .
git commit -m "changes made with claude code"
git push
```

---

## How the code is structured

You don't need to understand this to use the site, but it's useful
to know roughly what's in `index.html`:

```
<style> ... </style>       the design (colours, fonts, layout)
<nav> ... </nav>           the top navigation bar
<section class="hero">     the main content: name, bio, photos
<footer> ... </footer>     social links and location at the bottom
```

The colours are set at the top of the style section:

```css
--gold: #c8a96e;       the warm gold accent colour
--cream: #f0ebe0;      the off-white text colour
```

If you want to change a colour, tell Claude Code:
> "Change the gold accent colour to a darker bronze"

---

## If something goes wrong

**Site not updating after pushing?**
Wait a couple of minutes. If still nothing, check:
https://github.com/joeelliottmusic/joeelliottmusic.github.io/actions

**Git is asking for a username/password?**
This means the authentication token needs resetting. Ask Eleanor.

**You accidentally broke something?**
Don't panic. Run this to undo all unsaved changes:
```bash
git checkout -- index.html
```
Or ask Eleanor — every version of the site is saved in git history
and can be recovered.

---

## Quick reference

| What                          | Command                                                                  |
|-------------------------------|--------------------------------------------------------------------------|
| Go to website folder          | `cd /Users/joeelliott/Desktop/website/joeelliottmusic.github.io`        |
| Get latest changes            | `git pull`                                                               |
| Stage your changes            | `git add .`                                                              |
| Save a version with a message | `git commit -m "your message"`                                           |
| Send live                     | `git push`                                                               |
| Undo unsaved edits            | `git checkout -- index.html`                                             |
| See what's changed            | `git status`                                                             |
