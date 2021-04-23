<template>
  <main>

    <div class="body-wrap mt-3py-8 flex flex-col justify-center items-center">

      <h1 class="w-full mb-6 py-3 uppercase font-bold border-b border-main-500">About me</h1>

      <section id="aboutMe" class="infoCard about-con"> <!-- infoCard-con -->

        <div class="infoCard-img-con">
          <nuxt-img class="infoCard-img" src="/img/Headshot.jpg" alt="Kyle Hooper" loading="lazy" />
        </div>

        <div class="infoCard-text-con">
          <div class="infoCard-text">
            <p>Hey, thanks for taking the time to look at my portfolio. My name is Kyle Hooper, and I'm a recent graduate of the Mohawk College journalism program. I wear many hats when it comes to journalism, from on-camera personality to behind-the-scenes editor. I enjoy new challenges and working with a team to accomplish goals.</p>
            <p>I am looking to leverage my excellent storytelling skills and experience to contribute to high-quality work. Technologically adept, offering experience with many social media platforms, office technology programs, and advanced computer skills. Behind all of this, I love getting out to play hockey and enjoy gaming in my spare time. I'm open, honest and not afraid to say I don't know how to do something.</p>
          </div>
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