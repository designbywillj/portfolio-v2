<template>
  <div>
    <Header />
    <main>
      <nuxt />
    </main>
    <Footer />
  </div>
</template>

<script>
export default {
  components: {
    Header: () => import('@/components/Header'),
    Footer: () => import('@/components/Footer')
  },

  pageTransition: 'page'
}
</script>

<style lang="scss">
main {
  padding: 0 4rem;
  perspective: 200vw;
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
