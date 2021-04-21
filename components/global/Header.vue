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
  @apply text-main-400 text-4xl;

  &:hover {
    @apply text-gray-200;
  }
}

.header-con {
  @apply w-full flex flex-no-wrap items-center justify-between;
}

.nav-btn {
  @apply px-2 py-1 text-gray-400 bg-transparent transition duration-150 ease-in-out rounded border border-transparent;

  &:hover {
    @apply text-gray-200 bg-primary-700;
  }
  &:focus {
    @apply bg-primary-700 text-gray-200;
  }
}

.nav-con {
  @apply py-3 px-4 bg-transparent items-center justify-center;
}

.nav-links {
  @apply block mb-1 px-2 py-4 text-gray-300 text-center font-bold  uppercase text-2xl bg-transparent rounded;

  &:hover {
    @apply bg-primary-700 text-main-500;
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
    @apply mb-0 mx-1 px-3 py-2 text-base font-medium text-gray-300 bg-transparent;

    &:hover {
      @apply bg-primary-700 text-main-500;
    }
  }
}

.light-mode {
  & .header-main-con {
    @apply bg-primary-200
  }

  & .logo-link {
    @apply text-primary-700;

    &:hover {
      @apply text-main-700;
    }
  }

  & .nav-btn {
    @apply text-gray-600;

    &:hover {
      @apply text-primary-700 bg-primary-300;
    }
    &:focus {
      @apply text-primary-700 bg-primary-300;
    }
  }

  & .nav-links {
    @apply text-primary-600;

    &:hover {
      @apply bg-primary-500 text-gray-100;
    }
  }
}

@screen sm {
  .light-mode {
    & .nav-links {
      @apply px-0 py-1 mx-4 border-b-2 border-transparent text-gray-600 font-normal rounded-none;
      &:hover {
        @apply bg-transparent border-main-500 text-main-600;
      }
    }

  }
}

</style>
