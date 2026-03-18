<!--
  Image.stories.svelte

  Stories for the Image component.
  Image renders a responsive figure with an optional caption and photo credit.
  It handles both local asset paths (resolved via SvelteKit's asset()) and
  external URLs.

  Props:
  - src: Image source URL or local path starting with "/" (required)
  - alt: Descriptive alt text for accessibility (required)
  - caption: Optional caption text below the image
  - credit: Optional photo credit line
  - size: Layout size — "full" | "large" | "medium" | "small" (default: "full")
-->
<script module>
  import { defineMeta } from '@storybook/addon-svelte-csf';
  import Image from '$lib/components/Image.svelte';

  // A freely-licensed placeholder image for demonstrations
  const DEMO_IMAGE = 'https://picsum.photos/seed/liberty/1200/675';

  const { Story } = defineMeta({
    title: 'Components/Image',
    component: Image,
    tags: ['autodocs'],
    argTypes: {
      src: {
        control: 'text',
        description: 'Image URL or local path (local paths starting with "/" are resolved via asset())',
      },
      alt: {
        control: 'text',
        description: 'Descriptive alt text for screen readers and accessibility',
      },
      caption: {
        control: 'text',
        description: 'Optional caption displayed below the image',
      },
      credit: {
        control: 'text',
        description: 'Optional photo credit attribution',
      },
      size: {
        control: { type: 'select' },
        options: ['full', 'large', 'medium', 'small'],
        description: 'Controls the maximum width of the image',
      },
    },
    args: {
      src: DEMO_IMAGE,
      alt: 'View of New York Harbor at dawn',
    },
  });
</script>

<!-- Default: full-width image with caption and credit -->
<Story
  name="Default"
  args={{
    src: DEMO_IMAGE,
    alt: 'View of New York Harbor at dawn',
    caption: 'The harbor where generations of immigrants first glimpsed New York City and its famous skyline.',
    credit: 'Demo Image / NYCity News Service',
    size: 'full',
  }}
/>

<!-- No Caption: image displayed without any caption or credit -->
<Story
  name="No Caption"
  args={{
    src: DEMO_IMAGE,
    alt: 'View of New York Harbor at dawn',
    size: 'full',
  }}
/>

<!-- Caption Only: image with caption text but no photo credit -->
<Story
  name="Caption Only"
  args={{
    src: DEMO_IMAGE,
    alt: 'View of New York Harbor at dawn',
    caption: '"I lift my lamp beside the golden door," Emma Lazarus wrote in her 1883 sonnet "The New Colossus."',
    size: 'full',
  }}
/>

<!-- Large Size: constrained to max-width-image-large (720px) -->
<Story
  name="Large Size"
  args={{
    src: 'https://picsum.photos/seed/harlem/720/405',
    alt: 'A neighborhood street in upper Manhattan',
    caption: 'A neighborhood street in upper Manhattan, where Langston Hughes once lived and wrote.',
    credit: 'Demo Image / NYCity News Service',
    size: 'large',
  }}
/>

<!-- Medium Size: constrained to max-width-image-medium (480px) -->
<Story
  name="Medium Size"
  args={{
    src: 'https://picsum.photos/seed/tenement/480/270',
    alt: 'A historic tenement building on the Lower East Side',
    caption: 'A historic tenement building of the type documented by journalist Jacob Riis in the 1890s.',
    credit: 'Demo Image / NYCity News Service',
    size: 'medium',
  }}
/>

<!-- Small Size: constrained to max-width-image-small (320px) -->
<Story
  name="Small Size"
  args={{
    src: 'https://picsum.photos/seed/pressroom/320/320',
    alt: "A journalist's notebook and pen",
    caption: 'A reporter\'s notebook — symbol of the press freedoms protected by the First Amendment.',
    credit: 'NYCity News Service',
    size: 'small',
  }}
/>
