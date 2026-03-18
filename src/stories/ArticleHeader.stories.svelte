<!--
  ArticleHeader.stories.svelte

  Stories for the ArticleHeader component.
  ArticleHeader renders a large serif headline with a metadata box showing
  the byline and publication date in NYCity News Service style.

  Props:
  - headline: The main article title (required)
  - byline: Author name(s) (optional)
  - pubDate: Publication date in YYYY-MM-DD format (optional)
-->
<script module>
  import { defineMeta } from '@storybook/addon-svelte-csf';
  import ArticleHeader from '$lib/components/ArticleHeader.svelte';

  const { Story } = defineMeta({
    title: 'Components/ArticleHeader',
    component: ArticleHeader,
    tags: ['autodocs'],
    argTypes: {
      headline: {
        control: 'text',
        description: 'The main article title displayed as a large serif heading',
      },
      byline: {
        control: 'text',
        description: 'Author name(s) shown in the metadata box',
      },
      pubDate: {
        control: 'text',
        description: 'Publication date in YYYY-MM-DD format (e.g. "2024-01-15")',
      },
    },
  });
</script>

<!-- Default: full headline with byline and date -->
<Story
  name="Default"
  args={{
    headline: 'First Amendment at 230: Press Freedom Remains Cornerstone of American Democracy',
    byline: 'Emma L. Warren and Jack Hughes',
    pubDate: '2024-09-25',
  }}
/>

<!-- Headline Only: no byline or date -->
<Story
  name="Headline Only"
  args={{
    headline: "Statue of Liberty's Bronze Tablet Bears Emma Lazarus's Timeless Plea to the World",
  }}
/>

<!-- With Byline Only: headline and author, no date -->
<Story
  name="With Byline Only"
  args={{
    headline: "A Century After 'How the Other Half Lives,' Jacob Riis's Legacy Endures",
    byline: 'Rosa Riis',
  }}
/>

<!-- With Date Only: headline and date, no byline -->
<Story
  name="With Date Only"
  args={{
    headline: "Nellie Bly's Ten-Day Journey Transformed American Investigative Reporting",
    pubDate: '2024-11-14',
  }}
/>

<!-- Long Headline: tests wrapping behavior on narrow viewports -->
<Story
  name="Long Headline"
  args={{
    headline:
      "From Harlem to the Harbor: How the Dreams and Struggles of New York's Immigrants and Residents Shaped a City That Belongs to the World",
    byline: 'The NYCity News Service Investigative Team',
    pubDate: '2024-02-14',
  }}
/>
