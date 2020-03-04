<template>
  <article>
    <section class="hero">
      <h1>
        Will Johnson &mdash; creating impactful brands and products for the digital world.
      </h1>
    </section>
    <section>
      <Card />
      <Card />
    </section>
  </article>
</template>

<script>
export default {
  components: {
    Card: () => import('@/components/Card')
  },

  head() {
    return {
      title: 'Will Johnson - Graphic, Motion, and UX Designer',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Put an about description here'
        }
      ],
      script: [{ src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }]
    }
  }
}
</script>

<style lang="scss">
.hero {
  margin-bottom: 12rem;
}
</style>
