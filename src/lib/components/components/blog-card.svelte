<script lang="ts">
  interface Props {
    title: string;
    description: string;
    image: string;
    link: string;
  }

  const { title, description, link, image }: Props = $props();
</script>

<div class="flex flex-col items-center mb-8">
  <img src={image} alt="" class="rounded-3xl aspect-[376/262] h-62" />

  <div class="rounded-3xl bg-white drop-shadow-3xl p-6 flex flex-col gap-1.5 relative -mt-28 w-4/5">
    <h2 class="text-lg font-bold text-secondary leading-tight">{title}</h2>

    <p class="leading-relaxed mb-4">
      {description}
    </p>

    <a
      href={link}
      class={[
        " bg-gray-100 drop-shadow-lg rounded-full px-12 py-2 font-medium flex flex-row justify-between items-center mt-auto text-gray-700 mx-auto transition-all",
        "hover:bg-primary hover:text-white",
      ]}
    >
      Read More
    </a>
  </div>
</div>
