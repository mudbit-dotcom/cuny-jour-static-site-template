<!--
  Dashboard.stories.svelte

  Stories for the Dashboard component.
  Dashboard is a flex-row layout container designed to hold BigNumber stat cards
  side by side. It wraps on small screens so cards stack vertically on mobile.

  Props:
  - children: BigNumber (or other) components passed between opening/closing tags
-->
<script module>
  import { defineMeta } from '@storybook/addon-svelte-csf';
  import Dashboard from '$lib/components/Dashboard.svelte';
  import BigNumber from '$lib/components/BigNumber.svelte';

  const { Story } = defineMeta({
    title: 'Components/Dashboard',
    component: Dashboard,
    tags: ['autodocs'],
    parameters: {
      layout: 'padded',
    },
  });
</script>

<!-- Default: three BigNumber cards in a row -->
<Story name="Default">
  <Dashboard>
    <BigNumber number="5" label="First Amendment Freedoms" />
    <BigNumber number="72 Days" label="Nellie Bly's World Record" />
    <BigNumber number="1883" label="Year of 'The New Colossus'" />
  </Dashboard>
</Story>

<!-- Two Stats: two-card layout -->
<Story name="Two Stats">
  <Dashboard>
    <BigNumber number="330,000" label="People per Square Mile" />
    <BigNumber number="1 in 3" label="New Yorkers Born Abroad" footnote="Reflecting a city of newcomers" />
  </Dashboard>
</Story>

<!-- Four Stats: four-card layout that wraps on small screens -->
<Story name="Four Stats">
  <Dashboard>
    <BigNumber number="10 Days" label="Nellie Bly Undercover" />
    <BigNumber number="1890" label="'How the Other Half Lives' Published" />
    <BigNumber number="305 ft" label="Height of Statue of Liberty" />
    <BigNumber number="45" label="Immigrant Nationalities Documented" footnote="By Jacob Riis, Lower East Side" />
  </Dashboard>
</Story>

<!-- With Footnotes: stat cards with source attribution -->
<Story name="With Footnotes">
  <Dashboard>
    <BigNumber
      number="330,000"
      label="People per Square Mile"
      footnote="Lower East Side density, per Jacob Riis, 1890"
    />
    <BigNumber
      number="10 Days"
      label="Nellie Bly's Undercover Stay"
      footnote="Blackwell's Island asylum, 1887"
    />
    <BigNumber
      number="1791"
      label="Year Bill of Rights Ratified"
      footnote="Including First Amendment press protections"
    />
  </Dashboard>
</Story>
