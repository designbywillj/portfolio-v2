<template>
  <article>
    <section class="hero">
      <h1 class="hero__h1">
        Will Johnson &mdash; creating impactful brands and products for the digital world.
      </h1>
    </section>
    <section>
      <Card
        v-for="caseStudy in caseStudies"
        :key="caseStudy.title"
        :title="caseStudy.title"
        :category="caseStudy.category"
        :thumbnail="caseStudy.thumbnail"
        :description="caseStudy.description"
        :color="caseStudy.color"
        :link="'/case-study/' + titleToSlug(caseStudy.title)"
      />
    </section>
  </article>
</template>

<script>
export default {
  components: {
    Card: () => import('@/components/Card')
  },

  data() {
    return {
      caseStudies: []
    }
  },

  async asyncData() {
    const context = await require.context(
      '~/assets/content/case-study/',
      false,
      /\.json$/
    )

    const caseStudies = await context.keys().map((key) => ({
      ...context(key),
      id: key.replace('.json', '').replace('./', '')
    }))
    return {
      caseStudies
    }
  },

  methods: {
    titleToSlug(title) {
      return title.toLowerCase().replace(/\s/g, '-')
    }
  },

  head() {
    return {
      title: 'Will Johnson - Graphic, Motion, & UX Designer',
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
@import '@/assets/scss/variables';

.hero {
  margin-bottom: 6rem;

  @media (min-width: $breakpoint--md) {
    margin-bottom: 12rem;
  }

  &__h1 {
  }
}
</style>
