<!--
@component
This is your page!
-->

<svelte:head>
  <title>{headline} | NYCity News Service</title>
  <meta name="description" content="At the Craig Newmark Graduate School of Journalism..." />
  <link href="https://fonts.googleapis.com/css2?family=Playwrite+DK+Uloopet+Guides&display=swap" rel="stylesheet">
</svelte:head>

<script>
  // Import all the news furniture components
  import ArticleBody from '$lib/components/ArticleBody.svelte';
  import Image from '$lib/components/Image.svelte';
  import RelatedLinks from '$lib/components/RelatedLinks.svelte';
  import BigNumber from '$lib/components/BigNumber.svelte';
  import Dashboard from '$lib/components/Dashboard.svelte';
  import SplashHeader from '$lib/components/SplashHeader.svelte';
  

  // Article metadata
  let kicker = 'NYCity News Service';
  let headline = 'Become a Force for Good';
  let deck = "At CUNY's journalism school, change is in our DNA";
  let pubDate = 'March 22, 2026';

  // Related stories
  const relatedStories = [
    { headline: "How America's top news organizations escape rigid publishing systems to design beautiful data-driven stories on deadline.", href: 'https://palewi.re/docs/coding-the-news/' },
    { headline: 'How to install, configure and use Visual Studio Code, GitHub and Copilot', href: 'https://palewi.re/docs/coding-the-news/scripts/week-1/' },
    { headline: "How to publish a website with Node.JS and GitHub Actions", href:"https://palewi.re/docs/coding-the-news/scripts/week-2/"},
  ];
</script>

<!-- This sets the page title in the browser tab -->

<!-- Your page content goes here -->
<div class="container story-theme">
  <SplashHeader
    kicker={kicker}
    headline={headline}
    deck={deck}
    pubDate={pubDate}
  />
  
  <!-- Lead Image: Animated gif of students at the journalism school -->
  <Image
    src="/example-photo.gif"
    alt="The Craig Newmark Graduate School of Journalism is at 219 West 40th Street in Midtown Manhattan."
    caption="The Craig Newmark Graduate School of Journalism is at 219 West 40th Street in Midtown Manhattan."
    credit="Craig Newmark Graduate School of Journalism"
  />

<Dashboard>
  <BigNumber
    number="2006"
    label="Year Founded"
  />
  <BigNumber
    number="1,300"
    label="Alumni"
  />
  <BigNumber
    number="50%"
    label="Attend tuition free"
    footnote="As of Aug. 2025"
  />
/>
</Dashboard>
  <!-- Article Body: The main story text with proper typography -->
  <ArticleBody>
    <p>
      At the Craig Newmark Graduate School of Journalism at the City University of New York, change is in our DNA. That comes of being born in 2006, as the digital revolution was transforming our profession in ways none of us could have imagined.
    </p>

    <p>
      We fashioned a school to teach the latest storytelling, entrepreneurial, and technological skills alongside reporting, writing, and ethics. Beyond that, we’ve crafted a culture that spurns complacency, that isn’t afraid to pivot before the ground under us shifts.
    </p>

    <p>
      Our mission is to serve the public interest – by training new journalists from varied economic, racial, and cultural backgrounds who will bring much-needed diversity to newsrooms, by helping mid-career journalists retool their skills, and by partnering with other media organizations to find new paths to excellence.
    </p>

    <p>
      Our low tuition rates, along with the added backing of private donors, allow candidates for our master’s degrees in journalism and engagement journalism to receive a world-class education at an affordable price. We also offer a unique bilingual master’s in journalism for students fluent in English and Spanish.
    </p>

    <p>
      Our three media centers provide research, training, thought leadership, industry meet-ups, and financial support for quality journalistic work.
    </p>

    <p>
      We also offer a robust professional education program through regular evening and weekend workshops. And we support in-depth reporting projects of professional journalists through fellowship grants.
    </p>

    <p>
      Classes are led by accomplished full-time faculty and adjuncts, who tap their networks to help students and graduates find internships, freelance opportunities and — the ultimate prize — jobs.
    </p>

    <p>
      At a time when our profession is reeling from financial pressures and lack of trust, the Newmark Graduate School of Journalism is committed to producing the next generation of skilled, ethically minded, and diverse journalists.
    </p>

    <p>
      We invite you to be part of our world.
    </p>
  </ArticleBody>

  <!-- Related Stories: Links to other articles -->
  <RelatedLinks
    title="Related Stories"
    links={relatedStories}
  />

</div>
<style lang="scss">
  @use '$lib/styles' as *;

  :global(.story-theme) {
    --color-accent: #fe8807;
    --color-border: #fe8807;
}
</style>
