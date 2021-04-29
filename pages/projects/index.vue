<template>
  <main>
    <section v-if="posts" class="w-full max-w-5xl mx-auto">
      <h1 class="mb-6 px-3 py-3 uppercase font-bold border-b border-main-500">Projects</h1>
      <PostsIndex post-type="projects" :amount="99" />
    </section>
  </main>
</template>

<script>
export default {
  async asyncData({ $content, error }) {
    let posts;
    try {
      posts = await $content("projects").fetch();
    } catch (e) {
      error({ message: "Projects not found" });
    }
    return { posts };
  },
}
</script>
