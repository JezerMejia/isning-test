<script>
  import TestimonialCard from "../components/testimonial-card.svelte";
</script>

<div class={["flex flex-col gap-16 items-center my-12", "container mx-auto 2xl:max-w-7xl px-3"]}>
  <h1 class="text-6xl relative text-center font-serif text-secondary leading-tight">
    <span> Testimonials </span>
    <div
      class="absolute inset-x-0 -bottom-4 h-0.5 max-w-80 mx-auto from-transparent to-transparent via-primary bg-linear-to-r"
    ></div>
  </h1>

  <p class="text-xl text-center max-w-3xl">
    Don't just take our word for it—hear from our satisfied clients! We take pride in the string
    relationships we've built with our clients, and their feedback speaks to our commitment to
    exccelence.
  </p>

  <div class="grid grid-cols-1 md:grid-cols-2 gap-12">
    <TestimonialCard
      title="Laura Chen"
      description="Their attention to detail and professionalism exceeded our expectations. Highly recommend!"
      image="/gallery-1.webp"
      stars={4}
    />

    <TestimonialCard
      title="Laura Chen"
      description="Their attention to detail and professionalism exceeded our expectations. Highly recommend!"
      image="/gallery-2.jpeg"
    />
  </div>

  <a href="/testimonials" class="rounded-full bg-primary text-2xl text-white px-8 py-3 font-medium">
    Explore More Testimonials
  </a>
</div>
