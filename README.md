# h3x's personal website

This is the source code of my personal website.

It it built on [Zola](https://www.getzola.org/) with the [Tabi](https://github.com/welpo/tabi) theme.

## Progress

- Content stuff:
  - [x] Name and profile picture
  - [ ] Social links
  - [ ] Projects
  - [ ] Awesome links
- Style stuff:
  - [ ] Custom [skin](https://welpo.github.io/tabi/blog/customise-tabi/#skins)
- Devops stuff:
  - [x] README cleaned up
  - [ ] Deploy to `$service` + DNS

## Local development

1. [Install Zola](https://www.getzola.org/documentation/getting-started/installation/)
2. Clone your repository
3. Run `git submodule update --init --recursive`
4. Run `zola serve`
5. Visit <http://127.0.0.1:1111>

## Updating tabi

### Automated updates

This template includes a [GitHub Action workflow](https://github.com/h3x4d3c1m4l/personal-website/blob/main/.github/workflows/update-tabi.yml) that checks for tabi theme updates weekly and creates a PR when updates are available.

#### Setting up permissions

The automated updates require proper GitHub Actions permissions:

1. Go to your repository's Settings → Actions → General
2. Scroll down to "Workflow permissions"
3. Enable "Allow GitHub Actions to create and approve pull requests"
4. Save changes

<details>
<summary>How automated updates work (click to read)</summary>

- Every Monday at midnight (UTC), the workflow checks for new tabi versions
- If an update is found, it creates a PR with:
  - Detailed changelog
  - Links to relevant commits and PRs
  - The exact changes being made
- It runs the Test build workflow. If the build fails, you'll receive an email notification. **Verify the site works locally before merging the PR**
- You can review and merge these updates at your convenience

</details>

### Manual updates

```bash
git submodule update --remote themes/tabi
```
