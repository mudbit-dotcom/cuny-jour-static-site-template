<script>
  import ArticleHeader from '$lib/components/ArticleHeader.svelte';
  import ArticleBody from '$lib/components/ArticleBody.svelte';
  import Image from '$lib/components/Image.svelte';
  import RelatedLinks from '$lib/components/RelatedLinks.svelte';
  import Dashboard from '$lib/components/Dashboard.svelte';
  import BigNumber from '$lib/components/BigNumber.svelte';
  import SplashHeader from '$lib/components/SplashHeader.svelte';

  let kicker = 'Review';
  let headline = 'the lost potential of katseye';
  let deck = "A review of Katseye's lost potential";
  let pubDate = '2026-02-26'

  const relatedStories = [
    { headline: "Hearts2Hearts makes debut performance at Brooklyn Paramount.", href: 'https://palewi.re/docs/coding-the-news/' },
    { headline: 'BTS releases new album', href: 'https://palewi.re/docs/coding-the-news/scripts/week-1/' },
  ];
</script>

<svelte:head>
  <title>{headline} | the bitchy casual</title>
  <meta name="description" content="A review of Katseye's lost potential." />
  <link href="https://fonts.googleapis.com/css2?family=Coming+Soon&display=swap" rel="stylesheet" />
</svelte:head>

<div class="container">
<SplashHeader
    kicker={kicker}
    headline={headline}
    deck={deck}
    pubDate={pubDate}
  />

  <Image
    src="/katseye.gif"
    alt="Katseye performance"
    caption="Katseye performance"
    credit="Tenor GIF"
  />

  <Dashboard>
    <BigNumber number="2025" label="Year Released" />
    <BigNumber number="475 Million" label="Streams" />
    <BigNumber number=" Wheres Manon?" label="On hiatus" footnote="As of Feb. 2026" />
  </Dashboard>

 <ArticleBody>
  <p>Katseye is going through an identity crisis. And with their Black member Manon going on hiatus, the six-member girl group not only has a brand identity crisis on their hands, but a musical one too.</p>
  <p> Their debut performance of "Gnarly"—their viral hit song — at the 68th Grammy Awards was poorly received by fans. Likewise, their new single "Internet Girl," which was released in the beginning of this year, was met with frustration.</p>
</ArticleBody>

  <RelatedLinks
    title="Related Stories"
    links={relatedStories}
  />

</div>