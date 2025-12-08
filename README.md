# Archie A. Apa — Portfolio

This repository contains a Jekyll-based portfolio website built from the AcademicPages / Minimal Mistakes theme.

## Summary

- **Purpose:** personal portfolio and publications site for Archie A. Apa.
- **Tech:** Jekyll, Ruby, GitHub Pages-compatible, with optional Docker development environment.

## Repository highlights

- Site configuration: `_config.yml`
- Content: `_posts/`, `_talks/`, `_publications/`, `_pages/`, `_portfolio/`
- Static assets: `assets/`, `images/`, `files/`
- Site build and Docker: `Dockerfile`, `docker-compose.yaml`

## Quick start (local development)

### Prerequisites

- Ruby (recommended via system package manager or rbenv/rvm)
- Bundler (`gem install bundler`)
- Node.js and npm (for frontend tooling)

### Install and serve locally

```bash
# Install Ruby gems (from repo root)
bundle install

# Build & serve (live reload)
bundle exec jekyll serve -H 0.0.0.0 --config _config.yml

# Open http://localhost:4000
```

## Using Docker (recommended for reproducible environment)

```bash
# Build and run with docker compose
docker compose up --build

# The site will be available at http://localhost:4000
```

**Notes:**
- The `Dockerfile` uses `ruby:3.2` and installs dependencies from `Gemfile`.
- `docker-compose.yaml` mounts the repository into the container and runs Jekyll with `_config.yml` and `_config_docker.yml`.

## NPM scripts

- JavaScript assets are processed via npm scripts (see `package.json`). Common commands:
    - `npm run build:js` — produce `assets/js/main.min.js`
    - `npm run watch:js` — watch and rebuild JS on change

## Configuration and common edits

- **Site title and displayed name:** edit `title` and `name` in `_config.yml`.
    - The footer shows `{{ site.name | default: site.title }}` — change `name` to control the copyright line.
- **Add social links:** update the `author` keys in `_config.yml` (e.g. `github`, `linkedin`).
- **Hide RSS/feed:** set `atom_feed.hide: true` in `_config.yml` to remove the RSS link from the footer.

## Footer behavior

- The footer template is in `_includes/footer.html`. This repository shows links in the order: LinkedIn, GitHub, RSS (when enabled).

## Testing and preview

- After editing content or templates, restart Jekyll if using `bundle exec jekyll serve`.
- With Docker, `docker compose up` will pick up changes to mounted files automatically.

## Contributing

- See `CONTRIBUTING.md` for contribution guidelines.

## License

- This project uses the MIT License (see `LICENSE`).

## Maintainers & credits

- Built from the AcademicPages / Minimal Mistakes Jekyll theme.

## Contact

- Site author email: `archie.apa@gmail.com` (also configured in `_config.yml`)
