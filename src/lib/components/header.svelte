<script lang="ts">
  import { page } from "$app/state";
  import { Menu } from "lucide-svelte";
  import { cubicInOut, linear } from "svelte/easing";
  import { crossfade, fade, slide } from "svelte/transition";
  import { MediaQuery } from "svelte/reactivity";

  const websitePages = {
    Home: "/",
    "About us": "/about",
    Services: "/services",
    "Vintage Construction": "/vintage-construction",
    Gallery: "/gallery",
    Testimonials: "/testimonials",
    Blog: "/blog",
    FAQs: "/faqs",
  } as const;

  function active(path: string) {
    const pathname = page.url.pathname;
    if (path == "/") {
      return pathname == path;
    }
    return pathname.startsWith(path);
  }

  const [send, receive] = crossfade({
    duration: 250,
    easing: cubicInOut,
  });

  let openSidebar = $state(false);

  const large = new MediaQuery("min-width: 1024px");

  $effect(() => {
    if (large.current) {
      openSidebar = false;
    }
  });

  $effect(() => {
    if (openSidebar) {
      const body = document.querySelector("body");
      if (!body) return;
      body.style.overflow = "hidden";
    } else {
      const body = document.querySelector("body");
      if (!body) return;
      body.style.overflow = "";
    }
  });
</script>

{#snippet navLink(path: string, label: string)}
  {@const isActive = active(path)}
  <a
    href={path}
    class={[
      "px-3 py-1.5 text-center text-sm transition-all relative",
      "active:scale-95",
      "xl:text-base",
      "2xl:px-5",
    ]}
  >
    {#if isActive}
      <div
        class="absolute inset-x-0 -bottom-0.5 h-0.5 from-transparent to-transparent via-primary bg-linear-to-r"
        in:send={{ key: "active-navbar-tab" }}
        out:receive={{ key: "active-navbar-tab" }}
      ></div>
    {/if}

    {label}
  </a>
{/snippet}

<header class="container mx-auto p-3 2xl:max-w-7xl flex flex-row items-center justify-between">
  <img src="/logo.png" alt="Vintage Outdoor" class="w-24 h-24 object-cover mx-auto lg:mx-0" />

  <nav class="flex-row gap-2 items-center hidden lg:flex">
    {#each Object.entries(websitePages) as [label, path]}
      {@render navLink(path, label)}
    {/each}

    <a
      href="/#contact-us"
      class={[
        "bg-primary rounded-lg px-2 py-1.5 text-center transition-all text-white",
        "sm:min-w-32 sm:px-3",
        "hover:bg-primary/70",
        "active:scale-95",
      ]}
    >
      Contact Us
    </a>
  </nav>
</header>

<button
  class={[
    "border bg-white fixed top-0 left-0 mt-5 ml-5 p-3 z-50 transition-all",
    "lg:hidden",
    openSidebar && "ml-[280px]",
  ]}
  aria-label="Sidebar button"
  onclick={() => (openSidebar = !openSidebar)}
>
  <Menu class="text-secondary" />
</button>

{#if openSidebar}
  <div
    class="fixed w-[100vw] h-[100dvh] bg-black/20 z-20 inset-0 pointer-events-none"
    transition:fade={{ duration: 150 }}
  ></div>
  <nav
    class="fixed flex flex-col gap-2 items-start max-w-[280px] h-[100dvh] bg-white p-4 overflow-scroll z-50 inset-0"
    transition:slide={{ axis: "x", easing: linear, duration: 150 }}
  >
    {#each Object.entries(websitePages) as [label, path]}
      {@render navLink(path, label)}
    {/each}

    <a
      href="/#contact-us"
      class={[
        "bg-primary rounded-lg px-2 py-1.5 text-center transition-all text-white",
        "sm:min-w-32 sm:px-3",
        "hover:bg-primary/70",
        "active:scale-95",
      ]}
    >
      Contact Us
    </a>
  </nav>
{/if}
