<!--
  BigNumber.stories.svelte

  Stories for the BigNumber component.
  BigNumber displays a large statistic with a label — perfect for data dashboards
  in journalism projects.

  Props:
  - number: The value to display prominently (string or number)
  - label: Short description of the metric (string)
  - footnote: Optional small clarifying text below the label (string)
-->
<script module>
  import { defineMeta } from '@storybook/addon-svelte-csf';
  import BigNumber from '$lib/components/BigNumber.svelte';

  const { Story } = defineMeta({
    title: 'Components/BigNumber',
    component: BigNumber,
    tags: ['autodocs'],
    argTypes: {
      number: {
        control: 'text',
        description: 'The prominent value to display (e.g. "42%", "$1.2M", "3,500")',
      },
      label: {
        control: 'text',
        description: 'Short description of the metric displayed below the number',
      },
      footnote: {
        control: 'text',
        description: 'Optional small clarifying text below the label',
      },
    },
  });
</script>

<!-- Default: percentage stat with a label -->
<Story name="Default" args={{ number: '5', label: 'Freedoms in the First Amendment' }} />

<!-- With Footnote: includes optional clarifying text -->
<Story
  name="With Footnote"
  args={{
    number: '72 Days',
    label: "Nellie Bly's World Record",
    footnote: 'Around-the-world journey completed 1889–1890',
  }}
/>

<!-- Year: shows a four-digit year as a prominent stat -->
<Story name="Year" args={{ number: '1883', label: '"The New Colossus" Written by Emma Lazarus' }} />

<!-- Large Count: whole number example -->
<Story name="Large Count" args={{ number: '330,000', label: 'People per Square Mile' }} />

<!-- Ratio: shows ratio/fraction examples -->
<Story
  name="Ratio"
  args={{
    number: '1 in 3',
    label: 'New Yorkers Born Outside the U.S.',
    footnote: 'Reflecting a city of newcomers',
  }}
/>
