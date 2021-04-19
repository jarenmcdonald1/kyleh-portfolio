<template>
  <main>

    <div class="body-wrap mt-16 py-8 flex justify-center items-center">

      <section id="" class="contact-con">

        <h3>Say Hello</h3>
        <div class="contact-btns-con pt-4">
          <a class="btns" href="mailto:kyhooper5@gmail.com">
            <span>kyhooper5@gmail.com</span>
          </a>
        </div>

      </section>

    </div>

    <section class="index-sub-con hidden">
      <div class="sub-text-con">
        <div class="sub-text">
          <h4>Subscribe to my Newsletter!</h4>
        </div>
      </div>
      <div class="index-sub hidden">
        <div class="sub-input"></div>
        <div class="sub-submit"></div>
      </div>
    </section>

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