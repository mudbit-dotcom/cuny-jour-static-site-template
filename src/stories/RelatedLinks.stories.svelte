<!--
  RelatedLinks.stories.svelte

  Stories for the RelatedLinks component.
  RelatedLinks renders a "Related Stories" section at the end of an article —
  a list of links with a bold, uppercase, blue-accented heading.

  Props:
  - title: Section heading text (default: "RELATED STORIES")
  - links: Array of { headline, href } objects
-->
<script module>
  import { defineMeta } from '@storybook/addon-svelte-csf';
  import RelatedLinks from '$lib/components/RelatedLinks.svelte';

  const { Story } = defineMeta({
    title: 'Components/RelatedLinks',
    component: RelatedLinks,
    tags: ['autodocs'],
    argTypes: {
      title: {
        control: 'text',
        description: 'Section heading text displayed above the link list',
      },
      links: {
        control: 'object',
        description: 'Array of link objects, each with a headline and href property',
      },
    },
  });
</script>

<!-- Default: standard "Related Stories" section with several links -->
<Story
  name="Default"
  args={{
    title: 'RELATED STORIES',
    links: [
      {
        headline: 'The First Amendment at 230: What Five Freedoms Mean Today',
        href: '/first-amendment',
      },
      {
        headline: 'Emma Lazarus and the Making of "The New Colossus"',
        href: '/emma-lazarus',
      },
      {
        headline: 'How Jacob Riis Changed the Way New York Saw Itself',
        href: '/jacob-riis',
      },
    ],
  }}
/>

<!-- Custom Title: section with a different heading label -->
<Story
  name="Custom Title"
  args={{
    title: 'MORE ON THIS TOPIC',
    links: [
      { headline: "Nellie Bly's Undercover Journalism and Its Lasting Legacy", href: '/nellie-bly' },
      { headline: 'Langston Hughes and the Harlem Renaissance', href: '/langston-hughes' },
    ],
  }}
/>

<!-- Single Link: the minimum case — just one related story -->
<Story
  name="Single Link"
  args={{
    title: 'RELATED STORIES',
    links: [
      { headline: "E.B. White's New York: A City That Belongs to the World", href: '/eb-white-new-york' },
    ],
  }}
/>

<!-- No Links: renders nothing (component hides itself when links array is empty) -->
<Story
  name="No Links (Hidden)"
  args={{
    title: 'RELATED STORIES',
    links: [],
  }}
/>
