<template>
  <article class="case-study">
    <section class="case-study__title">
      <h4>{{ blogPost.category }}</h4>
      <h1>{{ blogPost.title }}</h1>
      <div
        :style="{ 'background-image': `url(${blogPost.feature})` }"
        class="case-study__feature"
      ></div>
    </section>

    <div class="case-study__body">
      <div class="case-study__content">
        <section class="case-study__section">
          <h2>{{ blogPost.description }}</h2>
        </section>

        <section class="case-study__details">
          <h4>Duration</h4>
          <p>{{ blogPost.duration }}</p>

          <h4>Role</h4>
          <p>{{ blogPost.role }}</p>

          <h4>For</h4>
          <p>{{ blogPost.for }}</p>
        </section>

        <section
          v-for="(item, index) in blogPost.section"
          :key="index"
          class="case-study__section"
        >
          <h2 v-if="item.heading">{{ item.heading }}</h2>
          <div v-if="item.content" v-html="$md.render(item.content)" />
        </section>
      </div>
    </div>
  </article>
</template>

<script>
export default {
  data() {
    return {
      blogPost: {}
    }
  },

  head() {
    return {
      title: this.blogPost.title + ' | Will Johnson. Graphic, Motion, & UX Designer',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Put an about description here'
        }
      ]
    }
  },
  async asyncData({ params, payload }) {
    if (payload) return { blogPost: payload }
    else
      return {
        blogPost: await require(`~/assets/content/case-study/${params.slug}.json`)
      }
  }
}
</script>

<style lang="scss">
@import '@/assets/scss/variables';

.case-study {
  &__title {
    h1 {
      margin-bottom: 2rem;

      @media (min-width: $breakpoint--md) {
        margin-bottom: 4rem;
      }
    }
  }

  &__feature {
    width: 100%;
    height: 20rem;
    background-size: cover;
    background-position: center;

    @media (min-width: $breakpoint--md) {
      height: 40rem;
    }
  }

  &__body {
    display: flex;
    justify-content: center;

    @media (min-width: $breakpoint--md) {
      flex-direction: row;
    }
  }

  &__content {
    flex: 0 0 100%;
  }

  &__details {
    flex: 0 0 100%;

    @media (min-width: $breakpoint--md) {
      flex: 0 1 40%;
      align-self: flex-start;
    }

    p {
      margin-bottom: 2rem;
    }

    h4,
    p {
      max-width: 800px;
      margin-right: auto;
      margin-left: auto;
    }
  }

  &__section {
    h2,
    p {
      max-width: 800px;
      margin-right: auto;
      margin-left: auto;
    }

    img {
      width: 100%;

      @media (min-width: $breakpoint--md) {
        margin-bottom: 2rem;
      }
    }

    p:last-child {
      img {
        margin-bottom: 0;
      }
    }
  }
}
</style>
