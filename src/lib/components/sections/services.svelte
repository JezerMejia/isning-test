<script>
  import { DraftingCompass, FileCog, PocketKnife } from "lucide-svelte";
  import ServiceCard from "../components/service-card.svelte";
</script>

<div class="bg-gray-50 w-full pt-16 pb-32">
  <div class={["container mx-auto 2xl:max-w-7xl px-3"]}>
    <h1 class="text-6xl relative text-center font-serif text-secondary">
      Our Services
      <div
        class="absolute inset-x-0 -bottom-3 h-0.5 max-w-80 mx-auto from-transparent to-transparent via-primary bg-linear-to-r"
      ></div>
    </h1>

    <p class="text-center mt-8 text-lg">
      Comprehensive solutions for your outdoor <br />
      and construction needs
    </p>

    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8 xl:gap-24 mt-14">
      <ServiceCard link="#" image="/service-1.jpg" title="Outdoor Living Spaces" icon={PocketKnife}>
        {#snippet content()}
          Reprehenderit voluptate adipisicing veniam ipsum nisi eu exercitation minim ipsum
          excepteur et cupidatat consequat. Laboris quis laboris ex labore amet sint voluptate ex
          nostrud excepteur dolor voluptate. Adipisicing dolor incididunt mollit minim cupidatat
          duis. Cupidatat ut dolor est.
        {/snippet}
      </ServiceCard>

      <ServiceCard
        link="#"
        image="/service-2.jpg"
        title="Landscaping Services"
        icon={DraftingCompass}
      >
        {#snippet content()}
          Reprehenderit voluptate adipisicing veniam ipsum nisi eu exercitation minim ipsum
          excepteur et cupidatat consequat. Laboris quis laboris ex labore amet sint voluptate ex
          nostrud excepteur dolor voluptate.
        {/snippet}
      </ServiceCard>

      <ServiceCard
        link="#"
        image="/service-3.avif"
        title="Vintage Construction Inc."
        icon={FileCog}
      >
        {#snippet content()}
          Reprehenderit voluptate adipisicing veniam ipsum nisi eu exercitation minim ipsum
          excepteur et cupidatat consequat. Laboris quis laboris ex labore amet sint voluptate ex
          nostrud excepteur dolor voluptate. Adipisicing dolor incididunt mollit minim cupidatat
          duis. Cupidatat ut dolor est.
        {/snippet}
      </ServiceCard>
    </div>
  </div>
</div>
