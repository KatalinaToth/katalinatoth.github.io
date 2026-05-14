# How to Update Your Website

This guide is for Libby Jenke (or anyone maintaining this site). All updates are done by editing files on GitHub — no terminal required.

---

## Adding a New Publication

1. Go to `content/publication/` on GitHub
2. Create a new folder with a kebab-case slug (e.g. `my-new-paper-title/`)
3. Inside that folder, create `index.md` with this template:

```yaml
---
title: "Your Paper Title"
date: 2026-01-01
authors:
  - Libby Jenke
  - Coauthor Name
publication_types: ["journal_article"]
publication: "Journal Name, Vol(Issue), Pages"
abstract: "Your abstract here..."
links:
  - name: Paper
    url: "https://link-to-paper.com"
tags:
  - relevant tag
  - another tag
---
```

4. For `publication_types`, use one of:
   - `journal_article` — peer-reviewed journal paper
   - `report` — working paper or under review
   - `book_chapter` — chapter in an edited volume

5. Commit the file. The site rebuilds automatically.

## Adding a PDF

1. Upload the PDF to `static/files/` on GitHub
2. In the paper's `index.md`, add a link:
   ```yaml
   links:
     - name: Article
       url: "files/your-paper.pdf"
   ```
   Note: do NOT put a leading `/` before `files/`.

## Updating Your Bio

Edit `content/bio/index.md`. The text below the front matter (`---`) is your bio page content.

To update the homepage intro, edit `content/_index.md`.

## Updating Your CV

Replace `static/files/jenke_cv2025.pdf` with the new version. To change the filename, also update the `cv_pdf` field in `content/_index.md`.

## Updating Contact Info

Edit `content/contact/index.md`.

## Updating Research Areas

Edit `data/research_areas.json`. Each area has subcategories, and each subcategory lists papers by their slug (the folder name in `content/publication/`).

## How Deployment Works

Every time you push to `main`, GitHub Actions automatically:
1. Builds the site with Hugo
2. Builds the search index with Pagefind
3. Deploys to GitHub Pages

No manual steps needed. If the build fails, you'll see a red X on your commit.
