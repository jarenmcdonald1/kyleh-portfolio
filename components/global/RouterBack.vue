<template>
  <nuxt-link @click.native="to ? null : $router.go(-2)" :to="to ? to : '/'">
    <svg class="h-4 mr-3 fill-current" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 157.19 280.92"><path d="M40.3,140.44c1.42,1.5,2.62,2.84,3.89,4.11Q97.4,197.8,150.6,251c6.67,6.68,8.28,14.46,4.5,21.2-5.23,9.31-17.21,11.63-25.23,4.52-5.6-5-10.74-10.46-16.05-15.76Q60.35,207.66,6.91,154.3-7,140.44,7,126.47,67.15,66.33,127.25,6.2c3.58-3.58,7.5-6.13,12.63-6.2,6.67-.09,12.12,2.43,15.23,8.55s2.82,12.35-1.63,17.8a131.83,131.83,0,0,1-9.32,9.75Q94.21,86.23,44.22,136.32C42.94,137.6,41.73,138.93,40.3,140.44Z"/></svg>
    <slot>GO BACK</slot>
  </nuxt-link>
</template>

<script>
export default {
  props: {
    to: { // ? Override with a path instead of router back
      type: String,
      default: '',
    },
  },
}
</script>