# Stories of Hope — website files

This is the full website. Upload every file below into your GitHub
repository, keeping the same names and the images/ folder structure.

## The pages

- `index.html` — homepage (includes live stats pulled from Firebase)
- `about.html` — about page: project intro, credits, funding, quote
- `stories.html` — Stories of Hope page (the live map: browse pins AND add your own story, both happen here)
- `living-proof.html` — "Living Proof" hub: three in-depth field stories
- `polderlab.html` — Living Proof subpage: the Polderlab, Netherlands
- `agroforestry.html` — Living Proof subpage: coffee agroforestry, Coto Brus, Costa Rica
- `philippines.html` — Living Proof subpage: Philippine crocodile conservation, Mabuwaya Foundation
- `styles.css` — controls colors, fonts, and layout for ALL pages at once
- `images/` — put your own photos in this folder

## How everything links together

```
index.html ──┬── about.html ──── living-proof.html
             │                          │
             └── stories.html           ├── polderlab.html
                 (the live map)         ├── agroforestry.html
                                         └── philippines.html
```

Every page's navigation bar links to: Home, About, Stories of Hope,
Living Proof. The three Living Proof subpages each have a
"← Back to Living Proof" link at the top and bottom.

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
2. Find the matching comment in the HTML (search for "EDIT" near a
   `style=""` attribute)
3. Change the empty `style=""` to:
   `style="background-image:url('images/hero.jpg');"`
4. Save and re-upload

On the three Living Proof subpages, the same trick works for the photo
strip (search `Photo 1`, `Photo 2`, `Photo 3`) and the hero banner.

## How to add a video to the homepage hero banner

The homepage hero (top banner) can show a looping background video
instead of a still photo, the same Schiermonnikoog photo is kept as a
"poster" image that shows while the video loads, and as a fallback on
phones that block autoplay video.

1. Upload your video file into your repository, e.g. `rainforest.mp4`
   at the top level (alongside `index.html`), or `images/rainforest.mp4`
   if you prefer to keep it in the images folder
   (keep the file under roughly 20MB so it loads quickly; if it's
   larger, compress it first with a free tool like HandBrake, or an
   online tool like freeconvert.com/video-compressor)
2. In `index.html`, find the `<video class="hero-video"` line near the top
3. Change `src="rainforest.mp4"` to match your actual filename and location
4. Save and re-upload

To remove the video and go back to a still photo only, delete the
whole `<video class="hero-video">...</video>` block.

## How to add a video to a Living Proof subpage

Each subpage (polderlab.html, agroforestry.html, philippines.html) has
a `<div class="video-frame">` block with a `<video>` tag inside.

**If your video is on YouTube or Vimeo:** delete the `<video>...</video>`
block and replace it with:

    <iframe src="https://www.youtube.com/embed/YOUR_VIDEO_ID" allowfullscreen></iframe>

**If you have your own video file:** upload the `.mp4` file into the
`images` folder, then change the empty `src=""` inside the `<source>`
tag to `src="images/your-video-file.mp4"`.

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
3. In every existing page's `<nav>` section, add a new line:
   `<a href="resources.html">Resources</a>`

## How to add a fourth Living Proof story

1. Copy `polderlab.html`, rename it (e.g. `new-story.html`)
2. Edit its content following the `EDIT THIS` comments
3. In `living-proof.html`, copy one whole `<a href="..." class="proof-tile">...</a>`
   block inside `<div class="proof-grid">` and point it at your new file

## Important: keep the map in sync

The planetary boundary names and colors on `stories.html` must always
match the `BOUNDARIES` list inside your map's `index.html` (in the
separate `solutions-hope-map` repository). If you ever add, remove, or
recolor a boundary in the map, update `stories.html` too.

## Live stats on the homepage

The three numbers on the homepage (`index.html`) are pulled live from
the same Firebase database the map uses. You don't edit these by hand;
they update automatically as students add stories to the map. If the
database can't be reached for any reason, the homepage shows a dash
(–) instead of a broken number.
