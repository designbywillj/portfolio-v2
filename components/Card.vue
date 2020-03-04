<template>
  <div class="card">
    <div class="card__thumbnail"></div>
    <div class="card__content">
      <h4>PRODUCT DESIGN</h4>
      <h2>Visuals By Impulse</h2>
      <p>
        What goes here is something about the product that may engage a viewer to interact
        with the case studies.
      </p>
      <nuxt-link to="/" class="card__button">
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
  name: 'Header',
  components: {}
}
</script>

<style lang="scss">
@import '@/assets/scss/colors';

.card {
  display: flex;
  padding-bottom: 12rem;

  &:last-child {
    padding-bottom: 4rem;
  }

  &__thumbnail {
    flex: 0 1 50%;
    padding-top: 37.5%;
    position: relative;
    background-image: url('/img/visuals_by_impulse_case_study.jpg');
    background-size: cover;
    background-position: 50%;
    transform-style: preserve-3d;
    transition: transform 0.25s cubic-bezier(0, 0, 0.5, 1);

    &::after {
      content: '';
      width: 100%;
      height: 100%;
      position: absolute;
      top: 4rem;
      left: 4rem;
      z-index: -1;
      transform: translateZ(-1em);
      background: linear-gradient(
        180deg,
        rgba(0, 206, 124, 0) 0%,
        rgba(0, 206, 124, 0.25) 100%
      );
      transition: transform 0.25s cubic-bezier(0, 0, 0.5, 1);
    }

    &:hover {
      transform: translate3d(-0.75rem, -0.75rem, 0) rotate(2deg);

      &::after {
        transform: translate3d(1.5rem, 1.5rem, -1em) rotate(-4deg);
      }
    }
  }

  &__content {
    flex: 0 1 50%;
    padding-top: 4rem;
    padding-left: 8rem;

    p {
      margin-bottom: 4rem;
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
}
</style>