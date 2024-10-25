---
layout: page
permalink: /website-notes/
title: Updating the website
description: 
nav: false
---

## Overview

This guide will help you update and maintain our lab's website. Most content edits require Markdown knowledge (using [Kramdown](https://kramdown.gettalong.org/quickref.html)). For significant changes, you might want to preview them locally with Jekyll, though it isn't required.

Here's what you'll find in this guide:
- [Previewing Changes Locally](#previewing-changes-locally)
- [Repository Structure](#repository-structure)
- [Adding Lab Members](#adding-lab-members)
- [Adding Publications](#adding-publications)
- [Adding News](#adding-news)
- [Creating a New Page](#creating-a-new-page)
- [Managing GitHub Security Alerts](#managing-github-security-alerts)
- [Adding New Plugins](#adding-new-plugins)

## Previewing Changes Locally (Optional)

If you'd like to preview your changes before pushing them to GitHub, follow these steps:

1. Install [Ruby and Jekyll](https://jekyllrb.com/docs/installation/#guides).
2. Clone the repository:
   ```
   git clone git@github.com:HyperMatrix/HyperMatrix.github.io.git
   ```
3. Navigate to the project folder and run:
   ```
   bundle install
   ```
4. Build and preview the site locally:
   ```
   bundle exec jekyll serve
   ```
   Then open [http://localhost:4000](http://localhost:4000) in your browser.

Refreshing the page will show your edits instantly. If you change configuration files (e.g., `_config.yml`), you'll need to restart the server.

## Repository Structure

Understanding the repo structure will make it easier to find what you need:

- **`_pages/`**: Markdown files for pages (e.g., homepage, about). PDFs are in the `content` subfolder.
- **`assets/`**: Images and other media files.
- **`_sass/`**: CSS styles. Colors are set in `_variables.scss`.
- **`_includes/`, `_layouts/`**: HTML files that control page structure.
- **`_config.yml`**: Site configuration and metadata.
- **Other folders** (`_bibliography/`, `_data/`, `_plugins/`): Not currently used, but may be useful in the future.

## Adding Lab Members

To add a new member to the website:

1. Open [_pages/about.md](https://github.com/HyperMatrix/HyperMatrix.github.io/blob/main/_pages/about.md).
2. Add the following to the relevant section:
   ```
   - name: "The Name"
     description: "Job title, date"
     website: "example.com"  # Remove if not applicable
     picture: "hyper_matrix.png"  # Replace with name.jpg if adding a new photo
   ```
3. If you are adding a new picture, upload it to [assets/img](https://github.com/HyperMatrix/HyperMatrix.github.io/tree/main/assets/img).

To add a new section for members, define it in `groups` at the top of the file, and create the section as shown below:
```yaml
newgroup:
  title: "New Group"
  people:
    - name: "First Last"
      description: "Job Title"
      picture: "name.jpg"
```

## Adding Publications

To add a publication:

1. Copy the BibTeX reference of the paper.
2. Add it to `_bibliography/papers.bib`.

Make sure the following fields are filled out:
- **year**
- **month**
- **author**
- **url**
- **booktitle**

Papers are displayed in reverse chronological order.

## Adding News

1. Open [_pages/about.md](https://github.com/HyperMatrix/HyperMatrix.github.io/blob/main/_pages/about.md).
2. Edit the `news_items` section:
   ```yaml
   news_items:
     - date: 2024
       title: "Accepted Papers 2024"
       content: "2 papers (NeurIPS), 2 papers (NAACL), 2 papers (EMNLP)"
   ```

Add new items at the top to keep the news updated.

## Creating a New Page

1. Create a new markdown file in [_pages](https://github.com/HyperMatrix/HyperMatrix.github.io/tree/main/_pages).
2. Include a YAML header:
   ```yaml
   ---
   layout: page
   permalink: /new-page-slug/
   title: "New Page Title"
   description: "Optional description"
   nav: true  # Set to false if not in the navigation bar
   nav_order: 6  # Lower numbers appear further left
   ---
   ```
3. Add the content below the header.

## Managing GitHub Security Alerts

GitHub might issue security alerts for dependencies. If this happens:

1. Check for a Dependabot pull request and merge it if available.
2. If there is no automatic PR, you can generate one via the [security tab](https://hypermatrixlab.github.io/security).
3. Alternatively, update manually by editing the [Gemfile](https://hypermatrixlab.github.io/blob/main/Gemfile) and running:
   ```
   gem install gem-name-here
   gem update gem-name-here
   bundle update gem-name-here
   bundle install
   ```

## Adding New Plugins

1. Add the plugin to `_config.yml` under the `plugins` list.
2. Add it to the [Gemfile](https://hypermatrixlab.github.io/blob/main/Gemfile).
3. Install the plugin:
   ```
   gem install gem-name-here
   bundle install
   ```

