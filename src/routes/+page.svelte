<!--
@component
This is your page!
-->
<script>
  // Import all the news furniture components
  import ArticleHeader from '$lib/components/ArticleHeader.svelte';
  import ArticleBody from '$lib/components/ArticleBody.svelte';
  import Image from '$lib/components/Image.svelte';
  import RelatedLinks from '$lib/components/RelatedLinks.svelte';

  // Article metadata
  let headline = 'The Torch and the Press: New York\'s Tradition of Free Expression';
  let byline = 'NYCity News Service';
  let pubDate = '2026-01-31';

  // Related stories
  const relatedStories = [
    { headline: 'The First Amendment: Five Freedoms That Shape American Journalism', href: '#' },
    { headline: 'Emma Lazarus and the Poem That Redefined the Statue of Liberty', href: '#' },
    { headline: 'How Nellie Bly Invented Modern Investigative Reporting', href: '#' },
  ];
</script>

<!-- This sets the page title in the browser tab -->
<svelte:head>
  <title>{headline} | NYCity News Service</title>
  <meta name="description" content="From the First Amendment to the lamp beside the golden door, New York has always been the city where press freedom and the stories of ordinary people matter most." />
</svelte:head>

<!-- Your page content goes here -->
<div class="container">
  
  <!-- Article Header: Headline, byline, and publication date -->
  <ArticleHeader
    {headline}
    {byline}
    {pubDate}
  />

  <!-- Lead Image: Placeholder image representing New York Harbor -->
  <Image
    src="https://picsum.photos/seed/liberty/1200/675"
    alt="View of New York Harbor at dawn"
    caption="The harbor where generations of immigrants first glimpsed New York City and its famous skyline."
    credit="Demo Image / NYCity News Service"
  />

  <!-- Article Body: The main story text with proper typography -->
  <ArticleBody>
    <p>
      The First Amendment to the United States Constitution, ratified in December 1791 as part of
      the Bill of Rights, guarantees five essential freedoms: religion, speech, the press, peaceful
      assembly, and the right to petition the government. For journalists, that second clause —
      "Congress shall make no law… abridging the freedom… of the press" — remains the cornerstone
      of a free and independent news media.
    </p>

    <p>
      New York has always been the city where those freedoms are tested most publicly. From the
      penny press of the 1830s to the muckrakers of the Progressive Era to today's digital
      newsrooms, the city's reporters have pushed at the boundaries of what the press can say
      and show.
    </p>

    <p>
      Among those who pushed hardest was Jacob Riis, a Danish-born immigrant who arrived in New
      York in 1870 with little money and no connections. After years of poverty and struggle, he
      found work as a police reporter and used his position to shine a light on the tenement
      conditions of the Lower East Side. His 1890 book, "How the Other Half Lives," documented
      the overcrowded, unsanitary living conditions endured by hundreds of thousands of immigrants
      — and helped spark lasting reforms.
    </p>

    <p>
      Around the same time, journalist Nellie Bly was transforming what investigative reporting
      could be. In 1887, she feigned mental illness to gain admission to the Women's Lunatic
      Asylum on Blackwell's Island, spending ten days documenting cruel and inhumane conditions
      inside. Her subsequent series in the New York World sparked immediate reforms and helped
      establish undercover journalism as a legitimate tool of public service. Two years later she
      traveled around the world in 72 days, beating Jules Verne's fictional record.
    </p>

    <p>
      The city's harbor, meanwhile, had become the first sight of America for millions of
      immigrants. When Emma Lazarus wrote "The New Colossus" in 1883, she gave the Statue of
      Liberty — still being assembled at the time — a voice: "Give me your tired, your poor, your
      huddled masses yearning to breathe free." Her words, engraved on the pedestal, would become
      the nation's most enduring welcome to newcomers.
    </p>

    <p>
      Decades later, those newcomers and their descendants were still reshaping the city. In
      Harlem, poet Langston Hughes asked what becomes of dreams when they are endlessly deferred —
      a question as urgent as the conditions Riis had photographed fifty years earlier. Hughes's
      writing gave voice to a generation navigating the gap between American promise and American
      reality.
    </p>

    <p>
      New York, as E.B. White observed in his 1949 essay about the city, belongs above all to
      those who come from somewhere else — who have chosen it deliberately, and who have remade
      themselves in its image. It is both the destination at the end of a long journey and the
      starting point for something new.
    </p>

    <p>
      That tradition of arrival, reinvention, and bearing witness is the inheritance of every
      journalist who works in this city. The stories that matter most — about justice, inequality,
      freedom, and the lives of ordinary people — are still being told.
    </p>

    <p>
      We invite you to tell them.
    </p>
  </ArticleBody>

  <!-- Related Stories: Links to other articles -->
  <RelatedLinks
    title="Related Stories"
    links={relatedStories}
  />

</div>
