<script>
  import BlogCard from "../components/blog-card.svelte";
</script>

<div class={["flex flex-col gap-16 items-center my-12", "container mx-auto 2xl:max-w-7xl px-3"]}>
  <h1 class="text-6xl relative text-center font-serif text-secondary leading-tight">
    <span> Our Blog </span>
    <div
      class="absolute inset-x-0 -bottom-4 h-0.5 max-w-80 mx-auto from-transparent to-transparent via-primary bg-linear-to-r"
    ></div>
  </h1>

  <p class="text-xl text-center max-w-3xl">
    Whether you're looking for expert advice, project inspiration, or updates on our recent work,
    you'll find it all here. Explore our articles to stay informed and inspired!
  </p>

  <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 lg:gap-12 xl:gap-24">
    <BlogCard
      title="The Ultimate Guide to Home Remodeling"
      description="Trends and Tips"
      image="/gallery-1.webp"
      link="#"
    />

    <BlogCard
      title="Transform Your Outdoor Space"
      description="5 Essential Tips"
      image="/gallery-2.jpeg"
      link="#"
    />

    <BlogCard
      title="Sustainable Landscaping"
      description="Eco-Friendly Practices"
      image="/gallery-3.jpg"
      link="#"
    />
  </div>

  <a href="/blog" class="rounded-full bg-primary text-2xl text-white px-8 py-3 font-medium">
    Discover More
  </a>
</div>
