# Hugo Profolio

Hugo Profolio is a minimalist, responsive Hugo theme designed for developers, engineers, and professionals to showcase their resume, blog, and project portfolio with a clean and modern aesthetic. Inspired by the [Jekyll theme minimal-resume](https://github.com/murraco/jekyll-theme-minimal-resume), this theme adds blogging capabilities, a projects section, and extended configuration options.

## Features

- **Blog / Posts** — publish articles with tags, dates, and table-of-contents support
- **Projects section** — card-based grid with status badges, tags, date ranges, and links to GitHub, GitLab, Codeberg, or any external URL
- **Resume page** — structured resume with portrait, about text, skills, certificates, languages, and hobbies
- **Homepage** — hero section with social icons and a three-column expertise overview
- **Color schemes** — choose between `standard`, `blurple`, and `lightblurple`
- **Minimalist design** — clean, responsive layout; dark-mode-ready CSS variables
- **Navigation menus** — fully configurable via `hugo.toml`
- **Shortcodes** — `newtablink` and `page-toc` included

---

## Requirements

- [Hugo](https://gohugo.io/) **extended** edition, v0.112.0 or later (SCSS compilation requires the extended binary)

---

## Installation

### Option A — Git clone

```bash
git clone https://github.com/0hlov3/hugo-theme-hugoprofolio.git themes/hugo-theme-hugoprofolio
```

Then set the theme in your `hugo.toml`:

```toml
theme = "hugo-theme-hugoprofolio"
```

### Option B — Git submodule

```bash
git submodule add https://github.com/0hlov3/hugo-theme-hugoprofolio.git themes/hugo-theme-hugoprofolio
```

---

## Configuration

Below is a full example `hugo.toml` covering all supported parameters.

```toml
baseURL = "https://example.com/"
languageCode = "en-us"
title = "Hugo Profolio"
theme = "hugo-theme-hugoprofolio"

[menus]
  [[menus.main]]
  name   = "Home"
  pageRef = "/"
  weight  = 10

  [[menus.main]]
  name   = "Posts"
  pageRef = "/posts"
  weight  = 20

  [[menus.main]]
  name   = "Projects"
  pageRef = "/projects"
  weight  = 30

  [[menus.main]]
  name   = "Resume"
  pageRef = "/resume"
  weight  = 40

[params]
# Displayed in the homepage hero section
title    = "Alice"
subtitle = "Senior DevOps Engineer & Kubestronaut"
author   = "Alice"

# Filename inside static/images/ — shown as the hero portrait
SelfPortrait = "portrait.jpg"

[params.userinfo]
# Shown in the "My Expertise" section on the homepage
user_description = "Short bio or intro paragraph."
user_design      = "Text shown under the Design column."
user_code        = "Text shown under the Code column."
user_tools       = "Text shown under the Tools column."

[params.social]
# All fields are optional. Shown as icon links in the homepage hero.
email         = "you@example.com"
github        = "https://github.com/you"
gitlab        = "https://gitlab.com/you"
codeberg      = "https://codeberg.org/you"
linkedin      = "https://linkedin.com/in/you"
mastodon      = "https://fosstodon.org/@you"
medium        = "https://medium.com/@you"
stackoverflow = "https://stackoverflow.com/users/0"
twitter       = "yourhandle"        # handle only, no URL
matrix_url    = "matrix.to/#/@you:matrix.org"
```

---

## Content Sections

### Homepage (`/`)

The homepage is rendered from `layouts/home.html`. It reads from `[params]`, `[params.userinfo]`, and `[params.social]` in `hugo.toml`. No Markdown file is needed — the homepage is the site root.

---

### Blog Posts (`content/posts/`)

Create posts as Markdown files inside `content/posts/`. Supported frontmatter:

```toml
+++
title = "My Post"
date  = 2024-06-01T09:00:00Z
draft = false
tags  = ["kubernetes", "golang"]
+++
```

| Field   | Type     | Description                        |
|---------|----------|------------------------------------|
| `title` | string   | Post title                         |
| `date`  | datetime | Publication date                   |
| `draft` | bool     | Set `true` to exclude from builds  |
| `tags`  | list     | Tag list; rendered as linked pills |

---

### Projects (`content/projects/`)

Create a section index at `content/projects/_index.md`:

```yaml
---
title: "Projects"
---
Optional intro text shown below the heading.
```

Each project is a Markdown file in `content/projects/`. Full frontmatter reference:

```yaml
---
title: "My Project"
description: "A short description shown on the project card."
tags: ["go", "kubernetes", "open-source"]

# Repository / source links — all optional, show as buttons on the card
github:   "https://github.com/you/repo"
gitlab:   "https://gitlab.com/you/repo"
codeberg: "https://codeberg.org/you/repo"
external: "https://example.com/project"   # any external URL (e.g. product page)
demo:     "https://demo.example.com"       # live demo link

# Status badge — renders a colored pill on the card
# Supported values: active | wip | archived
status: "active"

# Project timeline — both fields are optional strings
# Use a year ("2024"), a year-month ("2024-03"), or "present" for ongoing
starts: "2024"
ends:   "present"
---

Optional long-form description shown on the project's detail page.
```

#### Frontmatter reference

| Field         | Type   | Description                                                   |
|---------------|--------|---------------------------------------------------------------|
| `title`       | string | Project name                                                  |
| `description` | string | Short summary shown on the card                               |
| `tags`        | list   | Technology tags; each tag links to `/tags/<tag>`              |
| `github`      | string | GitHub repository URL                                         |
| `gitlab`      | string | GitLab repository URL                                         |
| `codeberg`    | string | Codeberg repository URL                                       |
| `external`    | string | Any external link (project page, product site, etc.)          |
| `demo`        | string | Live demo URL                                                 |
| `status`      | string | `active` (green), `wip` (yellow), or `archived` (grey)        |
| `starts`      | string | Project start year/date, e.g. `"2023"`                        |
| `ends`        | string | Project end year/date, e.g. `"2025"`, or `"present"` if ongoing |

**Date range examples:**

```yaml
# Completed project
starts: "2022"
ends:   "2024"

# Ongoing project
starts: "2023"
ends:   "present"

# No dates (omit both fields)
```

---

### Resume (`content/Resume.md`)

The resume uses the `resume` layout. Create `content/Resume.md`:

```toml
+++
title    = "Resume"
date     = 2024-01-01T00:00:00Z
draft    = false
layout   = "resume"
image    = "/images/portrait.jpg"
author   = "Alice Wunderland"
about    = "Short bio paragraph shown in the sidebar."
skills   = ["Go", "Kubernetes", "Terraform", "AWS"]
languages     = ["English", "German"]
certificates  = ["CKA", "CKAD", "CKS"]
hobbies       = ["Hiking", "Reading"]
tags     = ["Resume"]
+++

## Work Experience

### Job Title — Company Name

- Bullet point describing your impact.
- Another achievement.

___

## Education

### Degree — University
```

#### Frontmatter reference

| Field          | Type   | Description                              |
|----------------|--------|------------------------------------------|
| `layout`       | string | Must be `"resume"` to use the resume template |
| `image`        | string | Path to portrait image (e.g. `/images/portrait.jpg`) |
| `author`       | string | Your name, displayed prominently         |
| `about`        | string | Short bio paragraph                      |
| `skills`       | list   | List of skill strings                    |
| `certificates` | list   | List of certificate/credential strings   |
| `languages`    | list   | Spoken languages                         |
| `hobbies`      | list   | Hobbies / interests                      |

The body content (Markdown below the frontmatter) is rendered as the main resume content — use headings and bullet lists for work history, education, etc.

---

## Shortcodes

### `newtablink`

Renders a link that opens in a new tab with `rel="noopener noreferrer"`.

```markdown
{{< newtablink "https://example.com" >}}Link text{{< /newtablink >}}
```

### `page-toc`

Renders the page's table of contents at the insertion point.

```markdown
{{< page-toc >}}
```

---

## Color Schemes

Three color schemes are bundled. Set the active scheme in your site's CSS pipeline or by selecting the appropriate SCSS file. Available options:

| File                      | Description                          |
|---------------------------|--------------------------------------|
| `colors-standard.scss`    | Light theme with warm orange accents |
| `colors-blurple.scss`     | Dark theme with blue-purple accents  |
| `colors-lightblurple.scss`| Light variant of the blurple palette |

---

## Contributing

Contributions are welcome. Please fork the repository and open a pull request. Make sure your changes align with the project's goals and design philosophy.

## License

This project is licensed under the [MIT License](./LICENSE).
