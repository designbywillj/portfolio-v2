<template>
  <div>
    <transition name="splash" mode="out-in">
      <div v-if="isLoading" class="splash">
        <client-only>
          <Lottie :loop="false" :keep="true" @complete="onSplashComplete" name="splash" />
        </client-only>
      </div>
    </transition>

    <Header />
    <main>
      <nuxt />
    </main>
    <Footer />
  </div>
</template>

<script>
import { toggleDocumentOverflow } from '@/util'

export default {
  components: {
    Lottie: () => import('@/components/Lottie'),
    Header: () => import('@/components/Header'),
    Footer: () => import('@/components/Footer')
  },

  data() {
    return {
      isLoading: true
    }
  },

  mounted() {
    toggleDocumentOverflow(this.isLoading)
  },

  methods: {
    onSplashComplete() {
      toggleDocumentOverflow((this.isLoading = false))
    }
  },

  pageTransition: 'page'
}
</script>

<style lang="scss">
@import '@/assets/scss/variables';
@import '@/assets/scss/colors';

.splash {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  padding-bottom: 8vh;
  background-color: $color--white;
  z-index: 9999;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;

  & .lottie {
    transform: scale(0.25);
  }

  &-leave-active {
    transition: opacity 0.5s cubic-bezier(0.8, 0, 1, 1);
    & .lottie {
      transition: transform 0.5s cubic-bezier(0.8, 0, 1, 1);
    }
  }
  &-leave {
    opacity: 1;
    & .lottie {
      transform: scale(0.25);
    }
  }
  &-leave-to {
    opacity: 0;
    & .lottie {
      transform: scale(1);
    }
  }
}

main {
  padding: 0 2rem;

  @media (min-width: $breakpoint--md) {
    padding: 0 4rem;
  }
}

article {
  max-width: 75rem;
  margin: 0 auto;
}

.page {
  &-enter-active,
  &-leave-active {
    transition: opacity 0.66s cubic-bezier(0.25, 0, 0, 1),
      padding-top 0.66s cubic-bezier(0.25, 0, 0, 1);
  }
  &-enter,
  &-leave-active {
    opacity: 0;
  }
  &-enter {
    padding-top: 8rem;
  }
}
</style>
