<script lang="ts">
  import Footer from "$lib/components/footer.svelte";
  import Header from "$lib/components/header.svelte";
  import "../app.css";

  let { children } = $props();
</script>

<Header />

<div class="mb-20 sm:mb-16 py-8 lg:py-12 flex flex-col gap-24">
  {@render children()}
</div>

<Footer />
