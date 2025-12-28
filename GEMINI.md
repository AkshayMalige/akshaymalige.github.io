# Gemini Context: al-folio (Jekyll Site)

## Project Overview
This project is a static website built using **Jekyll**, utilizing the **al-folio** theme. It is designed for academics to showcase their portfolio, CV, publications, and projects.

*   **Framework:** Jekyll (Ruby)
*   **Theme:** al-folio
*   **Styling:** SCSS, Bootstrap
*   **Templating:** Liquid
*   **Formatting:** Prettier

## Building and Running

### Local Development (Ruby)
1.  **Install Dependencies:**
    ```bash
    bundle install
    ```
2.  **Serve Locally:**
    ```bash
    bundle exec jekyll serve
    ```
    *   Access at: `http://localhost:4000/` (or port specified in output)
    *   Use `--livereload` for auto-updates.

### Docker Development
1.  **Run with Docker Compose:**
    ```bash
    docker-compose up
    ```
    *   This mounts the current directory, so changes are reflected immediately.

### Linting & Formatting
*   **Prettier:** Used for formatting Liquid, HTML, CSS, etc.
    ```bash
    npm install
    npx prettier --write .
    ```

## Key Directories & Files

*   **`_config.yml`:** Main site configuration (title, author, plugins, theme settings). **Modify this first for site-wide changes.**
*   **`_pages/`:** Static pages (About, CV, Projects, etc.). Note that `index.html` is often generated from one of these or `index.md`.
*   **`_posts/`:** Blog posts (Format: `YYYY-MM-DD-title.md`).
*   **`_projects/`:** Project portfolio entries.
*   **`_bibliography/papers.bib`:** BibTeX file for the Publications page.
*   **`_data/`:** structured data files (YAML):
    *   `cv.yml`: Content for the CV page.
    *   `socials.yml`: Social media links.
    *   `repositories.yml`: GitHub repositories to display.
*   **`_layouts/` & `_includes/`:** Liquid templates for page structure and reusable components.
*   **`assets/`:** Static assets (images, CSS, JS, PDF). `assets/img/` is standard for content images.

## Development Conventions

*   **Content:** Write content in Markdown (`.md`) or HTML (`.html`) with Front Matter (YAML header).
*   **Citations:** Add new publications to `_bibliography/papers.bib`. The site uses `jekyll-scholar`.
*   **Images:** Place images in `assets/img/`. Responsive images are handled via configuration.
*   **Styles:** Edit `_sass/` for style overrides. Avoid inline styles where possible.
*   **Navigation:** Controlled via `_config.yml` or `_data/navigation.yml` (if present, otherwise checked in `_includes/header.liquid`).

## Common Tasks

*   **Add a Blog Post:** Create a new file in `_posts/` following the naming convention.
*   **Add a Project:** Create a new file in `_projects/` and ensure the `projects` collection is enabled in `_config.yml`.
*   **Update CV:** Edit `_data/cv.yml` or `assets/json/resume.json`.
*   **Change Theme Color:** Edit `_sass/_variables.scss` or `_sass/_themes.scss`.
