<template>
  <article class="case-study">
    <section>
      <h4>{{ blogPost.category }}</h4>
      <h1 class="case-study__title">{{ blogPost.title }}</h1>
      <div
        :style="{ 'background-image': `url(${blogPost.feature})` }"
        class="case-study__feature"
      ></div>
    </section>

    <div class="case-study__body">
      <div class="case-study__content">
        <section>
          <h3>{{ blogPost.description }}</h3>
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
      <aside class="case-study__details">
        <h4>Duration</h4>
        <p>{{ blogPost.duration }}</p>

        <h4>Role</h4>
        <p>{{ blogPost.role }}</p>

        <h4>For</h4>
        <p>{{ blogPost.for }}</p>
      </aside>
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
      title: 'Case Study',
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
.case-study {
  &__title {
    margin-bottom: 4rem;
  }

  &__feature {
    width: 100%;
    height: 30rem;
    background-size: cover;
    background-position: center;
  }

  &__body {
    display: flex;
  }

  &__content {
    flex: 0 1 60%;
    padding-right: 4rem;
  }

  &__details {
    flex: 0 1 40%;
    padding-left: 4rem;

    p {
      margin-bottom: 4rem;
    }
  }

  &__section {
    img {
      width: 100%;
    }
  }
}
</style>
