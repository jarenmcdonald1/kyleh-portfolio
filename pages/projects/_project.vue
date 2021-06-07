<template>
  <main>
    <section v-if="post">

      <article>
        <nuxt-img
          v-if="post.cover"
          class="cover-image"
          :src="post.cover"
          :alt="post.title"
        />

        <div class="article-titles-con">
          <h1 class="mb-4">{{ post.title }}</h1>
          <span class="mb-3 flex flex-wrap justify-between items-center">
            <h6 class="mt-0 inline py-1 px-2 mr-1 bg-primary-500 text-gray-100 text-sm font-medium rounded-sm">{{ post.category }}</h6>
            <h6 class="mt-0 inline py-1 px-2">{{ formatDate(post.date) }}</h6>
          </span>
          <p v-if="post.clientname" class="mt-1 mb-3"><span class="font-bold">Client:</span> {{ post.clientname }}</p>
          <p v-if="post.description" class="mt-1 mb-8">{{ post.description }}</p>
        </div>

        <div v-if="post.videolink">
          <div class="embed-r-con">
            <iframe class="embed-r-item mx-auto" :src="`https://www.youtube.com/embed/${post.videolink}`"
                frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope;
                picture-in-picture" allowfullscreen
            >
            </iframe>
          </div>
        </div>

        <!-- <h6 class="inline py-1 px-2 mr-1 bg-gray text-white text-sm font-medium rounded-sm">{{ post.category }}</h6> -->
        <nuxt-content :document="post" />
        <div v-if="post.gallery" class="nuxt-content">
          <img
            v-for="image in post.gallery"
            class="image"
            :key="image.id"
            :src="image"
          >
        </div>
      </article>

      <nav class="mb-8 go-back-btn" aria-label="go back">
        <router-back class="link-btn" />
      </nav>
    </section>
  </main>
</template>

<script>
export default {
  async asyncData({ $content, params, error }) {
    let post;
    try {
      post = await $content("projects", params.project).fetch();
    } catch (e) {
      error({ message: "Project not found" });
    }
    return { post };
  },
  methods: {
    formatDate(dateString) {
      const date = new Date(dateString)
      return date.toLocaleDateString(process.env.lang) || ''
    }
  }
}
</script>
