<script lang="ts">
  import Blog from "$lib/components/sections/blog.svelte";
  import ContactHero from "$lib/components/sections/contact-hero.svelte";
  import ContactUs from "$lib/components/sections/contact-us.svelte";
  import FeaturedColumns from "$lib/components/sections/featured-columns.svelte";
  import Gallery from "$lib/components/sections/gallery.svelte";
  import Hero from "$lib/components/sections/hero.svelte";
  import Services from "$lib/components/sections/services.svelte";
  import Testimonials from "$lib/components/sections/testimonials.svelte";
  import { headDescription, headTitle } from "$lib/snippets/head.svelte";
</script>

<svelte:head>
  {@render headTitle("Vintage Outdoor Inc.")}
  {@render headDescription("Transforming Spaces, Building Dreams")}
</svelte:head>

<Hero />
<FeaturedColumns />
<Services />
<Gallery />
<Testimonials />
<Blog />
<ContactHero />
<ContactUs />
