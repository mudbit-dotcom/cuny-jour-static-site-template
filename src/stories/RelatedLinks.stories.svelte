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
        headline: 'Mayor Announces New Affordable Housing Initiative in Brooklyn',
        href: '/housing-initiative',
      },
      {
        headline: 'City Council Approves $4.2 Billion Infrastructure Bill',
        href: '/infrastructure-bill',
      },
      {
        headline: 'NYCHA Residents Demand Answers After Third Heating Failure This Winter',
        href: '/nycha-heating',
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
      { headline: 'A History of Public Housing in New York City', href: '/history-nycha' },
      { headline: 'What Experts Say About the Housing Crisis', href: '/expert-housing' },
    ],
  }}
/>

<!-- Single Link: the minimum case — just one related story -->
<Story
  name="Single Link"
  args={{
    title: 'RELATED STORIES',
    links: [
      { headline: 'Budget Talks Stall as Council Deadline Approaches', href: '/budget-talks' },
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
