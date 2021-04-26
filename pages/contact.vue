<template>
  <main>

    <div class="body-wrap mt-3py-8 flex justify-center items-center">

      <section id="" class="contact-con">

        <h3>Say Hello</h3>
        <div class="contact-btns-con pt-4">
          <a class="btns" :href="`mailto:${content.siteemail}`" title="Send me an email">
            <span>{{ content.siteemail }}</span>
          </a>
        </div>
        <div class="contact-btns-con icons pt-4">
          <a v-if="content.linkedinlink" class="btns icons" :href="`${content.linkedinlink}`" title="View my LinkedIn profile">
            <span class="sr-only">{{ content.linkedinlink }}</span>
            <font-awesome-icon class="icon" :icon="['fab','linkedin']" />
          </a>
          <a v-if="content.youtubelink" class="btns icons" :href="`${content.youtubelink}`" title="View my YouTube channel">
            <span class="sr-only">{{ content.youtubelink }}</span>
            <font-awesome-icon class="icon" :icon="['fab','youtube']" />
          </a>
          <a v-if="content.instalink" class="btns icons" :href="`${content.instalink}`" title="View my Instagram profile">
            <span class="sr-only">{{ content.instalink }}</span>
            <font-awesome-icon class="icon" :icon="['fab','instagram']" />
          </a>
          <a v-if="content.twitterlink" class="btns icons" :href="`${content.twitterlink}`" title="View my Twitter profile">
            <span class="sr-only">{{ content.twitterlink }}</span>
            <font-awesome-icon class="icon" :icon="['fab','twitter']" />
          </a>
        </div>

      </section>

    </div>

  </main>
</template>

<script>
export default {
  head() {
    return {
      script: [{ src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }],
    };
  },
  async asyncData({$content, error}) {
    let content;
    try {
      content = await $content('site/info').fetch();
    } catch (e) {
      error({ message: 'Sorry, site data not found'});
    }
    return {content};
  },
};
</script>