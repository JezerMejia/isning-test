<script lang="ts">
  import { Play, Quote, Star } from "lucide-svelte";

  interface Props {
    title: string;
    description: string;
    image: string;
    stars?: number;
  }

  const { title, description, image, stars = 5 }: Props = $props();
</script>

{#snippet fiveStars(stars: number)}
  <div class="flex flex-row gap-2">
    {#each { length: 5 } as _, i}
      <span class={[i < stars ? "text-primary" : "text-secondary"]}>
        <Star fill="currentColor" />
      </span>
    {/each}
  </div>
{/snippet}

<div class="flex flex-col items-start mb-20 xl:mb-8 relative">
  <div
    class={[
      "rounded-3xl bg-gray-50 drop-shadow-3xl p-6 pt-8 pb-28 flex flex-col gap-2 w-full relative",
      "xl:w-70/100 xl:pr-48 xl:pb-24",
    ]}
  >
    <h2 class="text-3xl text-secondary font-serif leading-tight">{title}</h2>

    <p class="leading-relaxed mb-10 xl:mb-14 text-sm">
      {description}
    </p>

    {@render fiveStars(stars)}

    <div class="absolute inset-0 m-auto flex items-center justify-center">
      <Quote fill="currentColor" class="text-gray-200 size-10" />
    </div>
  </div>

  <div
    class={[
      "absolute aspect-video w-[325px] self-center group -bottom-24",
      "xl:self-end xl:w-[360px] xl:my-auto xl:inset-y-0",
    ]}
  >
    <img
      src={image}
      alt=""
      class={[
        "rounded-3xl aspect-video h-full grayscale-75 transition-all",
        "group-hover:grayscale-0",
      ]}
    />
    <span class="absolute inset-0 m-auto bg-primary p-3 rounded-full size-fit opacity-80">
      <Play class="text-white" fill="currentColor" />
    </span>
  </div>
</div>
