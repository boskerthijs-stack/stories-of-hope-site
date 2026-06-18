# Stories of Hope — website files

This is the full website: 4 pages plus one shared stylesheet.

## The files

- `index.html` — homepage
- `about.html` — about page
- `stories.html` — Stories of Hope page (shows the live map)
- `add-story.html` — Add Your Story page (shows the live map, same as above)
- `styles.css` — controls colors, fonts, and layout for ALL pages at once
- `images/` — put your own photos in this folder

## How to edit text

Open any `.html` file in Notepad (Windows) or TextEdit in plain-text mode (Mac).
Press Ctrl+F (or Cmd+F) and search for `EDIT THIS` — every editable headline
and paragraph has a comment like this directly above it:

    <!-- EDIT THIS: homepage headline -->
    <h1>Every place has a story.</h1>

Just change the text between the tags (`<h1>...</h1>`), save, and re-upload
to GitHub the same way as before.

## How to add your own photos

1. Put your image file inside the `images` folder, e.g. `images/hero.jpg`
2. Find the matching comment in the HTML, e.g. in `index.html` near the hero
3. Change the empty `style=""` to:
   `style="background-image:url('images/hero.jpg');"`
4. Save and re-upload

## How to change colors site-wide

Open `styles.css`, look at the very top for this block:

    :root {
      --color-cream: #FAF6EE;
      --color-forest: #0F3D2E;
      --color-moss: #4A7856;
      --color-gold: #D4A24C;
      ...
    }

Change any hex code here and it updates everywhere on the site at once.

## How to add a new page

1. Copy `about.html`, rename the copy (e.g. `resources.html`)
2. Replace its content with whatever you want
3. In ALL FOUR existing pages' `<nav>` section, add a new line:
   `<a href="resources.html">Resources</a>`

## Important: keep the map in sync

The planetary boundary names and colors on `stories.html` and `add-story.html`
must always match the `BOUNDARIES` list inside `map.html`. If you ever add,
remove, or recolor a boundary in the map, update both website pages too.
