<template>
  <div class="card">
    <nuxt-link :to="link" class="card__thumbnail">
      <div
        :style="{
          background: `linear-gradient(
        180deg,
        #${color}00 0%,
        #${color}40 100%
      )`
        }"
        class="card__thumbnail-color"
      ></div>
    </nuxt-link>
    <div class="card__content">
      <h4>{{ category }}</h4>
      <nuxt-link :to="link">
        <h2>{{ title }}</h2>
      </nuxt-link>
      <p>{{ description }}</p>
      <nuxt-link :to="link" class="card__button">
        Read Case Study
        <span>
          <img src="/svg/right-arrow.svg" alt="" />
        </span>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
  components: {},
  props: {
    title: {
      type: String,
      default: 'Case Study Title'
    },
    category: {
      type: String,
      default: 'Category'
    },
    thumbnail: {
      type: String,
      default: null
    },
    description: {
      type: String,
      default:
        'What goes here is something about the product that may engage a viewer to interact with the case studies.'
    },
    color: {
      type: String,
      default: '000000'
    },
    link: {
      type: String,
      default: '/'
    }
  }
}
</script>

<style lang="scss">
@import '@/assets/scss/variables';
@import '@/assets/scss/colors';

.card {
  display: flex;
  padding-bottom: 6rem;
  flex-direction: column;

  @media (min-width: $breakpoint--md) {
    padding-bottom: 12rem;
    flex-direction: row;
  }

  &:last-child {
    padding-bottom: 4rem;
  }

  &__thumbnail {
    flex: 0 0 100%;
    padding-top: 75%;
    position: relative;
    background-image: url('/img/visuals_by_impulse_case_study.jpg');
    background-size: cover;
    background-position: 50%;
    transform-style: preserve-3d;
    transition: transform 0.25s cubic-bezier(0, 0, 0.5, 1);
    perspective: 600px;

    @media (min-width: $breakpoint--md) {
      flex: 0 1 50%;
      padding-top: 37.5%;
    }

    &-color {
      width: 100%;
      height: 100%;
      position: absolute;
      top: 0;
      left: 0;
      z-index: -1;
      display: none;
      transition: transform 0.25s cubic-bezier(0, 0, 0.5, 1);

      @media (min-width: $breakpoint--md) {
        display: block;
        transform: translate3d(4rem, 4rem, -0.25rem);
      }
    }

    @media (min-width: $breakpoint--md) {
      &:hover {
        transform: translate3d(-1rem, -1rem, 0) rotate(-4deg);
      }

      &:hover > &-color {
        transform: translate3d(6rem, 6rem, -0.25rem) rotate(6deg);
      }
    }
  }

  &__content {
    flex: 0 0 100%;
    padding-top: 3rem;

    @media (min-width: $breakpoint--md) {
      flex: 0 1 50%;
      padding-top: 4rem;
      padding-left: 8rem;
    }

    p {
      margin-bottom: 2rem;

      @media (min-width: $breakpoint--md) {
        margin-bottom: 4rem;
      }
    }
  }

  &__button {
    line-height: 3rem;
    font-weight: 600;
    display: inline-block;

    img {
      margin-left: 1rem;
      transition: margin-left 0.25s cubic-bezier(0, 0, 0.5, 1);
    }

    &:hover {
      img {
        margin-left: 1.5rem;
      }
    }
  }

  &:nth-child(even) {
    @media (min-width: $breakpoint--md) {
      flex-direction: row-reverse;

      .card__content {
        padding-right: 8rem;
        padding-left: 0;
        text-align: right;
      }

      .card__thumbnail {
        &-color {
          transform: translate3d(-4rem, 4rem, -0.25rem);
        }

        &:hover {
          transform: translate3d(1rem, -1rem, 0) rotate(4deg);
        }

        &:hover > .card__thumbnail-color {
          transform: translate3d(-6rem, 6rem, -0.25rem) rotate(-6deg);
        }
      }
    }
  }
}
</style>
