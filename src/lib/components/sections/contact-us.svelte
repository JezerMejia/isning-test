<script lang="ts">
  import { MapPin, Phone, type Icon as IconType } from "lucide-svelte";
</script>

{#snippet contactLink(path: string, label: string, type: string, Icon: typeof IconType)}
  <a href={path} class={["flex flex-row gap-4 items-center mt-6"]}>
    <span class="bg-primary p-2 text-white rounded-full">
      <Icon class="relative h-5 w-5" />
    </span>
    <div class="flex flex-col gap-0.5">
      <span class="font-bold">
        {type}
      </span>
      <span class="text-xl">
        {label}
      </span>
    </div>
  </a>
{/snippet}

<div class="bg-gray-50 w-full pt-16 pb-32">
  <div
    class={[
      "grid grid-cols-1 lg:grid-cols-5 gap-8 items-center",
      "container mx-auto 2xl:max-w-7xl px-3",
    ]}
  >
    <div class="col-span-1 lg:col-span-2">
      <h1
        class="text-6xl relative text-center lg:text-start font-serif text-secondary leading-tight"
      >
        <span> Ready to Get Started? </span>
        <div
          class="absolute inset-x-0 -bottom-4 h-0.5 max-w-80 mx-auto lg:mx-0 from-transparent to-transparent via-primary bg-linear-to-r"
        ></div>
      </h1>

      <p class="mt-8 text-xl">
        Whether you're planning a stunning outdoor retreat, or a major construction project, Vintage
        Outdoor Inc- and Vintage Construction Inc. are here to help.
      </p>
      <p class="mt-4 text-xl">
        Get in touch with us today to discuss your project, request a quote, or schedule a
        consultation.
      </p>

      {@render contactLink("tel:+1 760 350 5552", "760 350 5552", "Phone Number", Phone)}
      {@render contactLink(
        "#location",
        "123 Main Street, Suite 456, Your City, ST 78901",
        "Address",
        MapPin
      )}
    </div>

    <form
      class="flex flex-col gap-4 bg-white rounded-4xl px-12 py-10 col-span-1 lg:col-span-3 drop-shadow-xl"
      method="GET"
      action="/"
    >
      <h1 class="text-5xl font-bold">Send a Message</h1>
      <div class="flex flex-col gap-2">
        <label for="name" class="font-medium">Name</label>
        <input
          id="name"
          name="name"
          type="text"
          required
          class="border-b-2 border-gray-300 px-2 py-0.5 outline-none ring-0 focus:border-primary"
        />
      </div>
      <div class="flex flex-col gap-2">
        <label for="email" class="font-medium">E-mail address</label>
        <input
          id="email"
          name="email"
          type="email"
          required
          class="border-b-2 border-gray-300 px-2 py-0.5 outline-none ring-0 focus:border-primary"
        />
      </div>
      <div class="flex flex-col gap-2">
        <label for="message" class="font-medium">Message</label>
        <textarea
          id="message"
          name="message"
          required
          cols="30"
          rows="4"
          class="border-b-2 border-gray-300 px-2 py-0.5 outline-none ring-0 focus:border-primary"
        ></textarea>
      </div>

      <button
        type="submit"
        class="self-end px-8 mt-8 py-2 text-2xl rounded-2xl bg-primary text-white font-medium"
      >
        Submit
      </button>
    </form>
  </div>
</div>
