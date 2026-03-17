<!--
  ArticleBody.stories.svelte

  Stories for the ArticleBody component.
  ArticleBody is a wrapper that applies NYCity News Service typography to
  any HTML content — paragraphs, headings, links, blockquotes, and lists.

  Props:
  - children: Content passed between opening and closing tags (Svelte snippet)
-->
<script module>
  import { defineMeta } from '@storybook/addon-svelte-csf';
  import ArticleBody from '$lib/components/ArticleBody.svelte';

  const { Story } = defineMeta({
    title: 'Components/ArticleBody',
    component: ArticleBody,
    tags: ['autodocs'],
    parameters: {
      layout: 'padded',
    },
  });
</script>

<!-- Default: typical article with multiple paragraphs -->
<Story name="Default">
  <ArticleBody>
    <p>
      The First Amendment to the United States Constitution, ratified in December 1791 as part of
      the Bill of Rights, guarantees five essential freedoms: religion, speech, the press, peaceful
      assembly, and the right to petition the government.
    </p>
    <p>
      For journalists, the press clause carries particular weight. Courts have long recognized that
      a free press serves as a watchdog on government, giving citizens the information they need to
      hold power accountable. Without it, the other freedoms enshrined in the Constitution would be
      far harder to defend.
    </p>
    <p>
      "Congress shall make no law respecting an establishment of religion, or prohibiting the free
      exercise thereof; or abridging the freedom of speech, or of the press," the amendment reads.
      In the centuries since, those forty-five words have been tested, interpreted, and reaffirmed
      in courtrooms across the country.
    </p>
  </ArticleBody>
</Story>

<!-- With Subheadings: shows h2/h3 typography inside article body -->
<Story name="With Subheadings">
  <ArticleBody>
    <p>
      New York City has always been at once many things: a harbor of refuge, a stage for ambition,
      a place where the world's currents converge. It is the city of the newcomer and the longtime
      resident, of the street vendor and the financier.
    </p>
    <h2>A City of Arrivals</h2>
    <p>
      For generations, newcomers have poured into New York carrying little more than courage and a
      willingness to remake themselves. The harbor welcomed them first — and the city tested them
      afterward, offering neither pity nor guarantee, only possibility.
    </p>
    <h3>The Island at the Center of the World</h3>
    <p>
      The narrow island of Manhattan has served as a proving ground for dreamers from every corner
      of the globe. Its capacity to absorb and inspire remains, by any measure, its most
      astonishing feature.
    </p>
  </ArticleBody>
</Story>

<!-- With Blockquote: shows the NYCity-style blue-bordered pull quote -->
<Story name="With Blockquote">
  <ArticleBody>
    <p>
      Near the entrance to New York Harbor stands a figure known to millions: a robed woman raising
      a torch aloft, her pedestal carrying words that became the nation's most recognizable welcome.
    </p>
    <blockquote>
      <p>
        "Give me your tired, your poor, your huddled masses yearning to breathe free, the wretched
        refuse of your teeming shore. Send these, the homeless, tempest-tost to me, I lift my lamp
        beside the golden door!"
      </p>
    </blockquote>
    <p>
      — Emma Lazarus, "The New Colossus," 1883
    </p>
  </ArticleBody>
</Story>

<!-- With Links and Lists: shows inline link and list typography -->
<Story name="With Links and Lists">
  <ArticleBody>
    <p>
      In the 1880s, journalist and photographer Jacob Riis ventured into the tenements of
      Manhattan's Lower East Side with a camera and a reporter's eye for injustice. Read about his
      work at the <a href="https://www.loc.gov">Library of Congress</a>.
    </p>
    <ul>
      <li>Families of six or more sharing a single windowless room</li>
      <li>Buildings without running water or adequate sanitation</li>
      <li>Child laborers as young as six working in garment factories and sweatshops</li>
    </ul>
    <p>
      "Long ago it was said that one half of the world does not know how the other half lives,"
      Riis wrote in the introduction to his 1890 book. His photographs made that ignorance harder
      to sustain.
    </p>
  </ArticleBody>
</Story>
