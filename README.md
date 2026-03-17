A simple SvelteKit starter template for ["JOUR 73361: Coding the News,"](https://github.com/palewire/cuny-jour-73361-coding-the-news) a course taught at the City University of New York's Craig Newmark Graduate School of Journalism 

## Quick Start

1. Click the green "Use this template" button on GitHub
2. Clone your new repository to your computer
3. Open the project in VS Code
4. Open a terminal and run:

```bash
npm install
npm run dev
```

5. Open http://localhost:5173 in your browser
6. Edit `src/routes/+page.svelte` to customize your page

### Deployment

Your site will automatically deploy to GitHub Pages when you push to the `main` branch. To enable this:

1. Go to your repository **Settings** > **Pages**
2. Under "Source", select **GitHub Actions**

That's it! Every push to `main` will automatically build and deploy your site to `https://<your-github-username>.github.io/<your-repository-name>/`

## Component Documentation (Storybook)

This template includes a [Storybook](https://storybook.js.org/) documentation app that demonstrates every component and the core SvelteKit patterns used in this project.

### Run Storybook locally

```bash
npm run storybook
```

Open http://localhost:6006 in your browser to browse the interactive component library.

### What's documented

| Component | Description |
|-----------|-------------|
| `BigNumber` | Large stat display for data dashboards |
| `SiteHeader` | Animated masthead with optional navigation |
| `SiteFooter` | CUNY-branded footer |
| `ArticleHeader` | Headline and metadata (byline, date) |
| `ArticleBody` | Typography wrapper for article text |
| `Image` | Responsive figure with caption and photo credit |
| `RelatedLinks` | "Related Stories" section with styled link list |
| `Dashboard` | Flex-row layout container for stat cards |

### Published Storybook

When deployed to GitHub Pages, the Storybook is published alongside the main site at:

```
https://<your-github-username>.github.io/<your-repository-name>/storybook/
```

The live Storybook for this template is at:

https://palewire.github.io/cuny-jour-static-site-template/storybook/

### Adding stories

Story files live in `src/stories/` and use the `.stories.svelte` format powered by [`@storybook/addon-svelte-csf`](https://github.com/storybookjs/addon-svelte-csf). Each story file corresponds to one component and contains multiple named variants that demonstrate different props and states.

