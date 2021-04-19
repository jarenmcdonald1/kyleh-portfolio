<template>
  <main>

    <section class="hidden self-center flex flex-col flex-1 items-center justify-center">
      <h1 class="title text-center font-serif">Nuxt — Tailwind — Netlify CMS</h1>
      <h2 class="subtitle text-center">Boilerplate</h2>
    </section>

    <section class="banner-con">
      <nuxt-img class="banner-img" src="/img/laptop-pexels.jpg" alt="laptop" />
      <div class="banner-text-con">
        <div class="banner-text">
          <h2>Kyle <span class="font-thin">Hooper</span></h2>
          <h4 class="font-thin mb-6">Digital Content Creator</h4>
          <nuxt-link class="mt-4 sm:mt-6 banner-btn" to="/#aboutMe" title="learn more">
            About Me
          </nuxt-link>
        </div>
      </div>
    </section>

    <section id="bannerLinks" class="banner-links-con">

        <nuxt-link class="banner-links-btn" to="/projects" title="view my projects">View some of my work</nuxt-link>

        <nuxt-link class="banner-links-btn" to="/contact" title="go to contact page">Let's talk!</nuxt-link>

    </section>

    <div class="body-wrap">

      <section id="whatIs" class="hidden infoCard-con">

        <div class="infoCard-img-con">
          <nuxt-img class="infoCard-img" src="/img/three-breads.jpg" alt="three healthy breads" loading="lazy" fit="cover" />
        </div>

        <div class="infoCard-text-con">
          <div class="infoCard-text">
            <h3>What is RMD Holistics?</h3>
            <p>RMD Holistics focuses on a complete approach to health and wellness. Our Holistic approach assess issues by digging down to the root of the problem to heal what is underneath the surface.</p>
            <p>RMD Holistics is designed to educate people, families, and a special focus on athletes and dancers. I have the experience of the conflict the body feels being pushed without the nutrition your individual body needs and the painful ways the body reacts. The difference between distress and healthy nutrition is optimal energy and strength.</p>
            <p>Combining the demands and effects that dance training has on young dancers with an interactive nutrition workshop will provide dancers, parents and studios with a strong foundation for optimal training and performance.</p>
            <p>Learn how to promote overall health and prevent disease!</p>
          </div>
        </div>

      </section>

      <section class="mt-8" id="indexBlogCon">
        <h3 class="mb-2 text-4xl uppercase border-b-2 border-main-500 pb-3">Projects:</h3>
        <posts post-type="projects" :amount="3" />
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
};
</script>