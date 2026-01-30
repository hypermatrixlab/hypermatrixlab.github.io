---
layout: page
permalink: /website-notes/
title: Website Maintenance Guide
description: Documentation for maintaining and updating the lab website
nav: false
---

## Quick Start

This guide covers everything you need to maintain our lab's website. Whether you're adding a new team member, publishing a paper, or creating a new page, you'll find step-by-step instructions below.

**New to Jekyll?** Don't worry—most updates only require basic Markdown editing. You can make changes directly on GitHub, and the site will rebuild automatically.

---

## Table of Contents

- [Making Your First Edit](#making-your-first-edit)
- [Common Tasks](#common-tasks)
  - [Adding Lab Members](#adding-lab-members)
  - [Adding Publications](#adding-publications)
  - [Adding News Items](#adding-news-items)
- [Advanced Tasks](#advanced-tasks)
  - [Creating a New Page](#creating-a-new-page)
  - [Local Development Setup](#local-development-setup)
  - [Adding Plugins](#adding-plugins)
- [Repository Structure](#repository-structure)
- [Troubleshooting](#troubleshooting)

---

## Making Your First Edit

The simplest way to update the website:

1. Navigate to the file you want to edit on [GitHub](https://github.com/hypermatrixlab/hypermatrixlab.github.io)
2. Click the pencil icon (✏️) to edit
3. Make your changes using [Markdown syntax](https://kramdown.gettalong.org/quickref.html)
4. Scroll down and commit your changes with a descriptive message
5. Wait 2-3 minutes for GitHub Pages to rebuild the site

**Pro tip:** You can preview Markdown formatting by clicking the "Preview" tab while editing.

---

## Common Tasks

### Adding Lab Members

**Location:** [`_pages/about.md`](https://github.com/hypermatrixlab/hypermatrixlab.github.io/blob/main/_pages/about.md)

1. Find the appropriate section (e.g., PhD Students, Postdocs, Alumni)
2. Add a new entry following this format:

```yaml
- name: "First Last"
  description: "PhD Student, 2024–Present"
  website: "https://example.com"  # Optional: remove if not applicable
  picture: "firstname_lastname.jpg"
```

3. If adding a photo, upload it to [`assets/img/`](https://github.com/hypermatrixlab/hypermatrixlab.github.io/tree/main/assets/img)
   - Recommended size: 400×400px
   - Format: JPG or PNG
   - Name: `firstname_lastname.jpg`

**To create a new member category:**

Add a new group at the top of `about.md`:

```yaml
groups:
  - newgroup

# Then define the section:
newgroup:
  title: "Research Scientists"
  people:
    - name: "First Last"
      description: "Research Scientist"
      picture: "firstname_lastname.jpg"
```

---

### Adding Publications

**Location:** [`_bibliography/papers.bib`](https://github.com/hypermatrixlab/hypermatrixlab.github.io/blob/main/_bibliography/papers.bib)

1. Get the BibTeX citation for your paper
2. Add it to `papers.bib`
3. Ensure these required fields are present:
   - `year`
   - `month`
   - `author`
   - `title`
   - `booktitle` (for conference papers) or `journal` (for journal articles)
   - `url` (link to paper or preprint)

**Example:**

```bibtex
@inproceedings{lastname2024title,
  title={Your Paper Title},
  author={Last, First and Last, First},
  booktitle={Conference on Neural Information Processing Systems},
  year={2024},
  month={December},
  url={https://arxiv.org/abs/2024.xxxxx}
}
```

Publications automatically appear in reverse chronological order on the website.

---

### Adding News Items

**Location:** [`_pages/about.md`](https://github.com/hypermatrixlab/hypermatrixlab.github.io/blob/main/_pages/about.md)

Find the `news_items` section and add new items at the **top** of the list:

```yaml
news_items:
  - date: "January 2025"
    title: "New Paper Accepted"
    content: "Our work on X was accepted to Y Conference."
  - date: "December 2024"
    title: "Lab Awards"
    content: "Congratulations to Jane for winning the Best Paper Award at NeurIPS!"
```

**Guidelines:**
- Keep entries concise (1-2 sentences)
- Use present tense for ongoing items, past tense for completed events
- Add new items at the top to maintain reverse chronological order

---

## Advanced Tasks

### Creating a New Page

1. Create a new Markdown file in [`_pages/`](https://github.com/hypermatrixlab/hypermatrixlab.github.io/tree/main/_pages)
   - Name it descriptively: `research-areas.md`, `publications.md`, etc.

2. Add the YAML front matter:

```yaml
---
layout: page
permalink: /research/
title: Research Areas
description: Overview of our research focus
nav: true
nav_order: 3
---
```

3. Write your content below the front matter using Markdown

**Front matter options:**
- `layout`: Usually `page` for standard pages
- `permalink`: URL path (must start and end with `/`)
- `title`: Page title shown in browser and navigation
- `description`: Optional meta description for SEO
- `nav`: Set to `true` to show in navigation bar
- `nav_order`: Lower numbers appear further left in navigation

**For PDF content:** Place PDF files in `_pages/content/` and link to them using:
```markdown
[Download PDF](/content/document.pdf)
```

---

### Local Development Setup

For testing changes before publishing, you can run the site locally.

**Prerequisites:**
- [Ruby](https://www.ruby-lang.org/en/documentation/installation/) (version 2.7 or higher)
- [Bundler](https://bundler.io/)

**Setup steps:**

```bash
# Clone the repository
git clone https://github.com/hypermatrixlab/hypermatrixlab.github.io.git
cd hypermatrixlab.github.io

# Install dependencies
bundle install

# Run local server
bundle exec jekyll serve

# Open http://localhost:4000 in your browser
```

The site will automatically rebuild when you save changes to files. For configuration changes (e.g., `_config.yml`), restart the server.

**Stopping the server:** Press `Ctrl+C` in the terminal.

---

### Adding Plugins

To extend the site's functionality with Jekyll plugins:

1. Add the plugin to `_config.yml`:

```yaml
plugins:
  - jekyll-sitemap
  - jekyll-seo-tag
  - your-new-plugin
```

2. Add it to the [`Gemfile`](https://github.com/hypermatrixlab/hypermatrixlab.github.io/blob/main/Gemfile):

```ruby
gem "your-new-plugin"
```

3. Install the plugin:

```bash
bundle install
```

4. Test locally before pushing to ensure compatibility

**Note:** GitHub Pages supports only [certain plugins](https://pages.github.com/versions/). For unsupported plugins, you'll need to use GitHub Actions for deployment.

---

## Repository Structure

Understanding the repository layout:

```
hypermatrixlab.github.io/
├── _pages/                 # Page content (Markdown files)
│   ├── about.md           # Homepage and team info
│   ├── content/           # PDF files and documents
│   └── *.md               # Other pages
├── _bibliography/          # Publication data
│   └── papers.bib         # BibTeX references
├── _sass/                  # Stylesheets
│   ├── _variables.scss    # Color schemes and variables
│   └── *.scss             # Component styles
├── _layouts/               # HTML templates
├── _includes/              # Reusable HTML components
├── assets/                 # Static files
│   ├── img/               # Images
│   └── css/               # Compiled CSS
├── _config.yml            # Site configuration
├── Gemfile                # Ruby dependencies
└── README.md              # Repository documentation
```

**Key files for common tasks:**
- Team members → `_pages/about.md`
- Publications → `_bibliography/papers.bib`
- News → `_pages/about.md`
- Site colors → `_sass/_variables.scss`
- Site metadata → `_config.yml`

---

## Troubleshooting

### Site not updating after commit

**Solution:** GitHub Pages can take 2-5 minutes to rebuild. Check the "Actions" tab on GitHub to see build status.

### Build failed

**Solution:** Check the "Actions" tab for error messages. Common issues:
- YAML syntax errors (indentation, missing quotes)
- Invalid BibTeX format
- Missing required front matter fields

### Images not displaying

**Solution:** 
- Verify the image file exists in `assets/img/`
- Check the file name matches exactly (case-sensitive)
- Ensure the path in Markdown is correct: `assets/img/filename.jpg`

### Markdown not rendering correctly

**Solution:**
- Review [Kramdown syntax](https://kramdown.gettalong.org/syntax.html)
- Ensure proper spacing around headers and lists
- Check for unclosed code blocks or quotes

### Local server won't start

**Solution:**
```bash
# Update bundler
gem update bundler

# Reinstall dependencies
bundle install

# Try running with bundle exec
bundle exec jekyll serve
```

### Changes not showing locally

**Solution:**
- Hard refresh your browser (`Ctrl+Shift+R` or `Cmd+Shift+R`)
- For `_config.yml` changes, restart the Jekyll server
- Clear your browser cache

---

## Getting Help

- **Jekyll Documentation:** [jekyllrb.com/docs](https://jekyllrb.com/docs/)
- **Markdown Guide:** [Kramdown Quick Reference](https://kramdown.gettalong.org/quickref.html)
- **GitHub Pages:** [docs.github.com/pages](https://docs.github.com/en/pages)

For lab-specific questions, reach out to the current web admin or open an issue on the repository.

---

*Last updated: January 2026*
