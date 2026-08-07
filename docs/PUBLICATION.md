# Publishing the handbook as a separate repository

The DevBits site remains private. The Android Interview Handbook becomes public only after it contains enough reviewed material to be useful.

## Before extraction

- Confirm `handbook/` contains no private site code or unpublished business information.
- Confirm all MDX follows `docs/MDX_CONTRACT.md`.
- Choose and add the public content license.
- Replace temporary publication notes in `README.md`.
- Add the public repository URL to the DevBits site configuration.
- Run the full handbook and site validation suite.

## Create the public repository

Create `github.com/queiroz/android-interview-handbook` from the contents of this `handbook/` directory, not from the entire DevBits repository.

The public repository root should therefore contain:

```text
README.md
CONTRIBUTING.md
ROADMAP.md
SYLLABUS.md
QUESTION_INVENTORY.md
LICENSE
content/
assets/
diagrams/
docs/
templates/
```

## Re-import with Git subtree

After the public repository is created, replace the local `handbook/` directory with a subtree import:

```bash
git remote add handbook git@github.com:queiroz/android-interview-handbook.git

git subtree add \
  --prefix=handbook \
  handbook main \
  --squash
```

Pull reviewed public changes into DevBits:

```bash
git subtree pull \
  --prefix=handbook \
  handbook main \
  --squash
```

Push handbook changes authored from DevBits:

```bash
git subtree push \
  --prefix=handbook \
  handbook main
```


## Site visibility

The private DevBits site treats handbook `status` as a publication boundary:

- `published` pages are visible in production navigation, direct routes, search, and the sitemap.
- `draft` and `review` pages remain in the repository but are not exposed by the production site.
- In development, the default view still mirrors production. Add `?status=all`, `?status=draft`, `?status=review`, or `?status=published` to handbook routes to inspect a specific content set in the sidebar and open matching pages. These overrides are ignored in production.
- Published pages must not link to handbook pages that are not yet published, because those destinations intentionally return 404 in production. Add the follow-up link when the destination is published.

This allows the handbook to ship incrementally without maintaining a separate production content tree. Frontmatter remains the source of truth for visibility.

## Deployment rule

Do not pull the public repository during a production build. Sync the subtree, review the site, commit the exact handbook revision, and deploy that deterministic DevBits commit.

A later automation may open a private DevBits pull request whenever the public handbook changes.
