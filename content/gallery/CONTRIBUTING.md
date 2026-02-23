# Adding Photos to the Gallery

This guide explains how to add new photo albums to the club website gallery. Follow these steps to publish photos from events, runs, and other club activities.

---

## Album structure

Each album is a folder inside `content/gallery/`. The folder contains two things:

```
content/gallery/your-album-name/
  index.md          ← title, date, description, and gallery display code
  images/
    photo-001.jpg
    photo-002.jpg
    photo-003.jpg
```

Use a short, descriptive folder name with hyphens instead of spaces (e.g. `summer-run-2024`, `agm-2025`).

---

## Step 1: Create the album folder and index.md

Create a new folder under `content/gallery/`. Inside it, create a file called `index.md` with the following content — copy and paste this template exactly, then fill in the title, date, and description:

```markdown
---
title: "Your Album Title"
date: 2024-06-15
description: "A short description of this photo collection"
---

{{< gallery match="images/*" rowHeight="150" margins="5" thumbnailResizeOptions="600x600 q85 Lanczos webp" imageResizeOptions="1200x1200 q90 Lanczos webp" previewType="blur" embedPreview=true sortOrder="asc" >}}
```

**Frontmatter fields:**

- `title` — Appears as the album heading and on the gallery index card
- `date` — The date of the event (YYYY-MM-DD format)
- `description` — One sentence describing the photos; shown under the album title

**Optional: set a cover image**

By default, the first photo alphabetically is used as the album thumbnail on the gallery page. To choose a specific cover image, add a `cover` line to the frontmatter:

```yaml
cover: "images/photo-005.jpg"
```

---

## Step 2: Prepare your images

Place your photos in the `images/` subfolder inside your album folder.

**Supported formats:** JPG, JPEG, PNG, WebP

**Naming:** Use sequential names for easy ordering (e.g. `photo-001.jpg`, `photo-002.jpg`). The gallery displays photos in alphabetical order by filename.

**Before adding photos, resize large files to save repository space.** The website generates its own smaller thumbnails automatically, so there is no benefit to storing originals larger than 2000 pixels wide.

If you have ImageMagick installed, run this command inside the `images/` folder:

```bash
mogrify -resize 2000x2000\> -quality 85 *.jpg
```

This resizes any image wider or taller than 2000 pixels (smaller images are left unchanged), then saves at 85% quality.

**You do not need to create thumbnails manually.** Hugo generates all thumbnail sizes automatically when the site rebuilds.

---

## Step 3: Set a cover image (optional)

The gallery index page shows a cover thumbnail for each album. By default it uses the first image alphabetically. To use a different image, add the `cover` parameter to the frontmatter in `index.md`:

```yaml
---
title: "Summer Run 2024"
date: 2024-07-20
description: "Photos from the annual summer run through the Brecon Beacons"
cover: "images/photo-012.jpg"
---
```

---

## Step 4: Publish

Commit your new folder and files to the `main` branch and push to GitHub. The GitHub Actions workflow will rebuild the site automatically within a few minutes.

If you are not comfortable with Git, send your photos to the webmaster along with the album title, date, and a brief description.

---

## Example

The existing `club-photos` album is a working example of this structure:

```
content/gallery/club-photos/
  index.md
  images/
    photo-001.jpg
    photo-002.jpg
    photo-003.jpg
    photo-004.jpg
    photo-005.jpg
```

You can copy that folder as a starting point for a new album.

---

## Checklist

- [ ] Album folder created under `content/gallery/`
- [ ] `index.md` created with title, date, description, and gallery shortcode
- [ ] Photos placed in `images/` subfolder
- [ ] Photos resized to max 2000px wide if needed
- [ ] Committed and pushed to `main` branch
