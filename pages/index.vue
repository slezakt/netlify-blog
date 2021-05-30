<template>
  <main>
    <section class="self-center flex flex-col flex-1 items-center justify-center">
      <h1 class="title text-center">Nuxt — Tailwind — Netlify CMS</h1>
      <nuxt-content :document="page" />
    </section>
  </main>
</template>
<script>
import Logo from '~/components/Logo'
export default {
  async asyncData({ $content, error, params }) {
    let page;
    try {
      page = await $content("about").fetch();
    } catch (e) {
      error({ message: "Blog posts not found" });
    }
    return { page };
  },
}
</script>





