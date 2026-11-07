# Simple two-section landing page

A one-page site for GitHub Pages: two full-screen sections, each with a
background image, a main image on one side, and text on the other.

## Where things live

```
_config.yml              Site title, description, background shading
_sections/1-intro.md     Text + image settings for the first section
_sections/2-contact.md   Text + image settings for the second (contact) section
images/                  All your pictures
assets/style.css         Colours, fonts, spacing (optional to touch)
index.html               Page structure (you shouldn't need to edit this)
```

## Editing text

Open a file in `_sections/` and change everything below the second `---` line.
It's Markdown:

- `# Big heading`, `## Smaller heading`
- Blank line between paragraphs
- `**bold**`
- `[link text](https://example.com)`, `[email me](mailto:you@example.com)`
- End a line with two spaces to break onto a new line without a gap

## Changing images

Easiest: upload a new picture into `images/` with the **same file name** as
the one you're replacing (e.g. `section-1-background.jpg`).

Or upload it with any name and update the matching line at the top of the
section file:

```yaml
background: images/my-photo.jpg   # fills the whole section
image: images/portrait.jpg        # the main image off to one side
image_alt: Short description      # read aloud by screen readers
image_side: left                  # left or right
```

Tips: backgrounds look best around 1920 px wide; main images around 900 px
wide, portrait or square. Keep each file under ~500 KB so the page loads fast.

## Changing sizes

At the top of `assets/style.css`:

```css
--section-height: 50vh;  /* 50vh = both sections fit on one screen */
--image-height: 36vh;    /* main image height, as a share of the screen */
```

`vh` means "percent of the screen height", so everything scales with the
monitor. On phones the image stacks above the text and the page scrolls.

## Adding or removing a section

Sections appear in file-name order. Copy `2-contact.md` to `3-something.md`
to add a third; delete a file to remove it.

## Publishing on GitHub Pages

1. Create a new repository on GitHub. Name it `yourusername.github.io` for the
   address `https://yourusername.github.io`, or anything else for
   `https://yourusername.github.io/repo-name/`.
2. Upload all these files and folders (keep the folder structure — including
   the folders that start with `_`).
3. In the repository go to **Settings → Pages**. Under *Build and deployment*
   choose **Deploy from a branch**, pick `main` and `/ (root)`, and save.
4. Wait a minute or two, then refresh the Pages settings to see your link.

Any later edit you commit (even straight in the GitHub website) republishes
the site automatically.
