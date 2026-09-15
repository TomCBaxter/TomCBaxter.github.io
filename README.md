# TomCBaxter.github.io

Personal academic website for Thomas Baxter, PhD astrophysics student at the
Astrophysics Research Institute, Liverpool John Moores University. Live at
<https://tomcbaxter.github.io/>.

Built with Jekyll, currently configured as a publications-first site (blog,
projects, and teaching collections are disabled).

## Running locally

Preferred: open this repo in a dev container (VS Code "Reopen in Container",
or GitHub Codespaces) — it provisions Ruby, ImageMagick, and everything else
automatically and serves the site on attach.

Alternatively, with Docker installed:

```bash
docker compose pull && docker compose up
# site runs at http://localhost:8080
```

## Where content lives

- `_bibliography/papers.bib` — publications, rendered via jekyll-scholar
- `_pages/` — site pages (about, publications, CV, personal, etc.)
- `assets/img/` — images, processed into responsive WebP at build time
- `assets/json/resume.json` — CV data

See [AGENTS.md](AGENTS.md) for build commands and contributor guidelines.

## License

MIT — see [LICENSE](LICENSE). Built on the
[al-folio](https://github.com/alshedivat/al-folio) Jekyll theme.
