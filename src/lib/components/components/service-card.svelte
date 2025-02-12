<script lang="ts">
  import { type Icon as IconType } from "lucide-svelte";
  import type { Snippet } from "svelte";

  interface Props {
    title: string;
    content: Snippet;
    image: string;
    link: string;
    icon: typeof IconType;
  }

  const { title, content, link, image, icon: Icon }: Props = $props();
</script>

<div class="bg-white rounded-3xl p-6 flex flex-col gap-3 drop-shadow-3xl">
  <img src={image} alt="" class="rounded-t-2xl aspect-[338/318]" />

  <h2 class="text-4xl text-primary font-serif mt-2">{title}</h2>

  <p class="text-sm leading-relaxed mb-4">
    {@render content()}
  </p>

  <a
    href={link}
    class={[
      "text-xl bg-gray-100 drop-shadow-lg rounded-full px-8 py-3 font-medium flex flex-row justify-between items-center mt-auto text-gray-700 transition-all",
      "hover:bg-primary hover:text-white",
    ]}
  >
    Read More
    <span class="rounded-full aspect-square bg-primary p-2">
      <Icon class="text-white" />
    </span>
  </a>
</div>
