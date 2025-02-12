<script lang="ts">
  import { MapPin, Phone, type Icon as IconType } from "lucide-svelte";
  import Whatsapp from "./icons/whatsapp.svelte";
  import Facebook from "./icons/facebook.svelte";
  import Linkedin from "./icons/linkedin.svelte";
  import Twitter from "./icons/twitter.svelte";

  const companyPages = {
    Home: "/",
    "About us": "/about",
    Services: "/services",
    "Vintage Construction": "/vintage-construction",
    Gallery: "/gallery",
  } as const;

  const supportPages = {
    Testimonials: "/testimonials",
    Blog: "/blog",
    FAQs: "/faqs",
    "Contact Us": "/#contact-us",
  } as const;
</script>

{#snippet navLink(path: string, label: string)}
  <a href={path} class={["text-start transition-all relative", "active:scale-95"]}>
    {label}
  </a>
{/snippet}

{#snippet socialLink(path: string, label: string, Icon: typeof IconType)}
  <a
    href={path}
    class={["p-2 transition-all relative bg-primary text-white rounded-full", "active:scale-95"]}
  >
    <Icon class="relative h-5 w-5" />
    <span class="sr-only">
      {label}
    </span>
  </a>
{/snippet}

{#snippet contactLink(path: string, label: string, Icon: typeof IconType)}
  <a href={path} class={["transition-all flex flex-row gap-4 items-center", "active:scale-95"]}>
    <span class="bg-primary p-2 text-white rounded-full">
      <Icon class="relative h-5 w-5" />
    </span>
    <span>
      {label}
    </span>
  </a>
{/snippet}

<div class="bg-gray-50 py-24 w-full">
  <footer class="container mx-auto p-3 2xl:max-w-7xl grid lg:grid-cols-6 gap-8">
    <div class="flex flex-col items-center gap-8 lg:col-span-2">
      <img src="/logo.png" alt="Vintage Outdoor" class="w-24 h-24 object-cover" />

      <p class="text-sm text-center">
        At Vintage Outdoor Inc. we are passionate about transforming your outdoor spaces into
        breahttaking landscapes that enhance your lifestyle.
      </p>

      <div class="flex flex-row items-center gap-2">
        {@render socialLink("#facebook", "FaceBook", Facebook)}
        {@render socialLink("#whatsapp", "WhatsApp", Whatsapp)}
        {@render socialLink("#linkedin", "WhatsApp", Linkedin)}
        {@render socialLink("#twitter", "Twitter", Twitter)}
      </div>
    </div>

    <nav
      class="flex flex-row gap-16 items-start lg:col-span-4 justify-around lg:justify-between flex-wrap lg:flex-nowrap"
    >
      <ul class="list-none flex flex-col gap-4">
        <span class="text-2xl font-bold">Our Company</span>
        {#each Object.entries(companyPages) as [label, path]}
          <li>
            {@render navLink(path, label)}
          </li>
        {/each}
      </ul>

      <ul class="list-none flex flex-col gap-4">
        <span class="text-2xl font-bold">Support</span>
        {#each Object.entries(supportPages) as [label, path]}
          <li>
            {@render navLink(path, label)}
          </li>
        {/each}
      </ul>

      <div class="flex flex-col gap-8">
        <div class="relative flex flex-col gap-4">
          <label for="join-newsletter" class="text-2xl font-bold">Join Our Newsletter</label>
          <input
            name="join-newsletter"
            type="email"
            placeholder="Enter your email"
            class="rounded-2xl border px-3 py-2 pr-28"
          />
          <button
            class="absolute right-0 bottom-0 bg-primary py-2 px-4 rounded-2xl border border-black text-white"
          >
            Subscribe
          </button>
        </div>

        <ul class="list-none flex flex-col gap-4">
          <li>
            {@render contactLink("tel:+1 760 350 5552", "760 350 5552", Phone)}
          </li>
          <li>
            {@render contactLink(
              "#location",
              "123 Main Street, Suite 456, Your City, ST 78901",
              MapPin
            )}
          </li>
          <li>
            {@render contactLink(
              "mailto:office@vintageoutdoorinc.com",
              "office@vintageoutdoorinc.com",
              MapPin
            )}
          </li>
        </ul>
      </div>
    </nav>
  </footer>
</div>
