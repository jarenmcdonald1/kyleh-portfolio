<template>
  <main>

    <div class="body-wrap mt-3py-8 flex justify-center items-center">

      <section id="" class="contact-con">

        <h3>Say Hello</h3>
        <div class="contact-btns-con pt-4">
          <a class="btns" href="mailto:kyhooper5@gmail.com">
            <span>kyhooper5@gmail.com</span>
          </a>
        </div>
        <div class="contact-btns-con icons pt-4">
          <a class="btns icons" href="https://www.linkedin.com">
            <span class="sr-only">linkedin.com/youracct</span>
            li
          </a>
          <a class="btns icons" href="https://www.youtube.com">
            <span class="sr-only">youtube.com/youracct</span>
            yt
          </a>
          <a class="btns icons" href="https://www.instagram.com">
            <span class="sr-only">instagram.com/youracct</span>'i'
          </a>
          <a class="btns icons" href="https://www.twitter.com">
            <span class="sr-only">twitter.com/youracct</span>
            t
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
};
</script>