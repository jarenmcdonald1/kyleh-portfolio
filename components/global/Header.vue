<template>

  <header class="z-50 header-main-con sm:flex sm:justify-between sm:items-center">
    <div class="header-con">

      <div class="px-2 py-2 sm:py-1">
        <nuxt-link class="logo-link" to="/">
          <span class="font-black">K</span><span class="font-thin">H</span>
        </nuxt-link>
      </div>

      <div class="sm:hidden">
        <button @click="isOpen = !isOpen" class="nav-btn" type="button" aria-label="toggle mobile nav button">
          <svg class="h-8 w-8 fill-current" viewBox="0 0 24 24">
            <path v-if="isOpen" fill-rule="evenodd" d="M18.278 16.864a1 1 0 0 1-1.414 1.414l-4.829-4.828-4.828 4.828a1 1 0 0 1-1.414-1.414l4.828-4.829-4.828-4.828a1 1 0 0 1 1.414-1.414l4.829 4.828 4.828-4.828a1 1 0 1 1 1.414 1.414l-4.828 4.829 4.828 4.828z"/>
              <path v-if="!isOpen" fill-rule="evenodd" d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"/>
          </svg>
        </button>
      </div>
      
    </div>

    <nav :class="isOpen ? 'block' : 'hidden'" class="nav-con sm:flex">
      <nuxt-link class="nav-links" to="/#aboutMe">About</nuxt-link>
      <nuxt-link class="nav-links" to="/projects">Projects</nuxt-link>
      <nuxt-link class="nav-links hidden" to="/blog">Blog</nuxt-link>
      <nuxt-link class="nav-links" to="/contact">Contact</nuxt-link>
    </nav>

  </header>

</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      isOpen: false,
    }
  }
}
</script>

<style lang="postcss" scoped>

.header-main-con {
  @apply bg-primary-800 w-full py-2 px-3;
}

.logo-link {
  @apply text-gray-200 text-4xl;

  &:hover {
    @apply text-white;
  }
}

.header-con {
  @apply w-full flex flex-no-wrap items-center justify-between;
}

.nav-btn {
  @apply px-2 py-1 text-gray-200 bg-transparent transition duration-150 ease-in-out rounded border border-transparent;

  &:hover {
    @apply text-white bg-primary-600;
  }
  &:focus {
    @apply bg-primary-600 text-gray-200;
  }
}

.nav-con {
  @apply py-3 px-4 bg-transparent items-center justify-center;
}

.nav-links {
  @apply block mb-1 px-3 py-2 text-gray-200 text-center text-2xl bg-transparent rounded;

  &:hover {
    @apply bg-primary-600 text-white;
  }
}

@screen sm {
  .header-main-con {
    @apply py-0;
  }

  .nav-con {
    @apply flex;
  }

  .nav-links {
    @apply mb-0 mx-1 px-3 py-2 text-lg font-light text-gray-200 bg-transparent;

    &:hover {
      @apply bg-primary-600 text-white;
    }
  }
}

.light-mode {
  & .header-main-con {
    @apply bg-primary-200
  }

  & .logo-link {
    @apply text-primary-800;

    &:hover {
      @apply text-primary-600;
    }
  }

  & .nav-btn {
    @apply text-gray-600;

    &:hover {
      @apply text-white bg-primary-600;
    }
    &:focus {
      @apply text-white bg-primary-600;
    }
  }

  & .nav-links {
    @apply text-primary-600;

    &:hover {
      @apply bg-primary-600 text-white;
    }
  }
}

@screen sm {
  .light-mode {
    & .nav-links {
      @apply px-0 py-1 mx-4 border-b-2 border-transparent text-gray-600 font-normal rounded-none;
      &:hover {
        @apply bg-transparent border-primary-600 text-primary-700;
      }
    }

  }
}

</style>
