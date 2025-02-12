<script lang="ts">
  const gallery = [
    "/gallery-1.webp",
    "/gallery-2.jpeg",
    "/gallery-3.jpg",
    "/gallery-4.jpg",
    "/gallery-5.jpg",
  ];
</script>

<div
  class={[
    "grid grid-cols-1 lg:grid-cols-5 gap-8 items-center",
    "container mx-auto 2xl:max-w-7xl px-3",
  ]}
>
  <div class="lg:col-span-2">
    <h1 class="text-6xl relative text-center lg:text-start font-serif text-secondary leading-tight">
      <span>
        Explore<br />
        Our Gallery
      </span>
      <div
        class="absolute inset-x-0 -bottom-4 h-0.5 max-w-80 mx-auto lg:mx-0 from-transparent to-transparent via-primary bg-linear-to-r"
      ></div>
    </h1>

    <p class="mt-8 text-xl">
      Take a look at our recent projects to see the quality and creativity we bring to every job.
      Whether it's a beautifully landscaped garden or a newly built home, our portfolio showcases
      the best of what Vintage Outdoor Inc. and Vintage Construction Inc. can offer.
    </p>
  </div>

  <div class="grid grid-cols-12 gap-4 lg:col-span-3">
    {#each gallery as src}
      <img
        {src}
        alt=""
        class={[
          "col-span-4 aspect-[248/268] rounded-2xl object-cover h-[260px] w-full",
          "nth-[4]:col-span-5 nth-[4]:h-[200px]",
          "nth-[5]:col-span-7 nth-[5]:h-[200px]",
        ]}
      />
    {/each}
  </div>
</div>
