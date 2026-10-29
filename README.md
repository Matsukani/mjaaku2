# 宮古語入門 — public website

This repository contains the generated public website: a 目次 and Lesson 001, including explanations, exercises, and vocabulary.

## First publication

1. Open this repository's **Settings → Pages**.
2. Under **Build and deployment → Source**, select **GitHub Actions**. The workflow is already included; no template is needed.
3. Open **Actions → Publish lessons → Run workflow**, select `main`, and run it.
4. Wait for the `publish` job to succeed, then open its `github-pages` deployment link.

This public repository can use GitHub Pages on GitHub Free. No upgrade is needed for this setup.

## Editing and updating

The authoring source remains in the private working repository. This repository is a publication destination, not a second editable master.

Once the publication credential is configured in the private authoring repository, its **Update public site** workflow builds and commits the approved export here. Pushes changing `website/` automatically trigger **Publish lessons**. The manual **Run workflow** button remains available.

Continue editing the original Markdown in the authoring repository. Do not edit generated HTML here. Only pages explicitly selected for publication are exported. The source action needs a token with Contents read/write access to this public repository only; setup instructions live in the private repository's `docs/github-pages.md`. No private-repository credential is stored here.

`publication.json` records the source revision and file checksums. A build whose public output is unchanged creates no new public commit.

## Publication scope

The workflow uploads only `website/`. It contains:

- `index.html`: 目次
- `lessons/001-ga-nu/index.html`: Lesson 001
- `style.css`: shared presentation

The source lesson's wording, tables, exercises, and vocabulary are preserved. The derived page omits only the final repository navigation to the answer key and authoring notes, which are not published in this edition. The answer key requires reconciliation with the current exercise numbering before a later release.

Source datasets, research analyses, authoring notes, archives, and unpublished lessons are excluded. The publication workflow uses only this repository's contents and does not access the private working repository.
