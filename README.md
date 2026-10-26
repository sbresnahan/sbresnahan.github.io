# Sean T. Bresnahan — research website

Editable Jekyll source for `sbresnahan/sbresnahan.github.io`, published at
`https://seantbresnahan.com`.

**Computational genetics of the evolutionary and developmental origins of health and disease.**

## GitHub Pages

The contents of this directory belong at the repository root. Include the hidden
`.github/`, `.gitignore`, and `.ruby-version` files. Do not nest the site in a
`source/` folder in the repository, and do not upload the separate HTML preview.

1. Commit the source to a review branch in the existing repository.
2. In **Settings → Pages → Build and deployment**, select **GitHub Actions**.
3. Preserve **seantbresnahan.com** in the custom-domain setting.
4. Merge the reviewed changes into `main`.
5. Inspect **Actions → Build and deploy Jekyll site** for the build/deployment result.

The included `.github/workflows/pages.yml` builds with Ruby 3.2.3, Bundler 4.0.17,
and the checked-in Gemfile.lock. Pushes to `main` and manual workflow runs trigger
the workflow. No personal access token is needed in this package.

The full setup guide supplied with the v8 archive explains file placement,
existing-site migration, domain settings, previewing, and troubleshooting.

## Local source build

With Ruby 3.2.3 and native gem build prerequisites installed:

```bash
gem install bundler -v 4.0.17
bundle _4.0.17_ install
bundle _4.0.17_ exec jekyll serve
```

Use the URL Jekyll prints. Production builds use:

```bash
JEKYLL_ENV=production bundle _4.0.17_ exec jekyll build --destination _site --trace
```

The separate built preview in the archive needs only Node.js:
run `node serve-preview.cjs` **inside `preview/`**, then visit
`http://127.0.0.1:8000/`. Do not double-click HTML files.

## Editing content

- Biography/contact information: `_data/profile.yml`
- Research: `research.html`
- Research illustrations: `assets/images/research/`
- Original homepage overview: `assets/images/photos/research_program_overview.png`
- Individual news milestones: `_news/`
- Publication records: `_publications/`
- Navigation: `_data/navigation.yml`
- Theme styles: `assets/css/global.css`
- Shared icon/social metadata: `_includes/head_metadata.html`
- Original DNA icon: `assets/images/site_icon.png`
- Shared social-preview image: `assets/images/social_preview.png`
- Default social description, image dimensions, and alt text: `_config.yml`

Every page layout uses the same supplied social image, with page-specific titles
and URLs. Browser/device icon variants at the repository root were derived from
the supplied DNA icon. Upload the complete source to include these assets.
Replacing only `assets/images/site_icon.png` later will not regenerate the smaller
icon variants automatically; the workflow performs a Jekyll build, not image conversion.

Keep `url: "https://seantbresnahan.com"` and `baseurl: ""` for the existing root
custom-domain deployment. Generated `_site/`, dependencies, and caches are ignored.
Do not place private application PDFs or credentials in this public source.

## Theme attribution

The existing site is based on
[academic-homepage](https://github.com/luost26/academic-homepage).
Its original license is retained in `LICENSE`.
