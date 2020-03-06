<template>
  <footer class="footer">
    <div class="footer__content">
      <a href="mailto:hi@designbywillj.com" class="footer__email">hi@designbywillj.com</a>
      <div class="footer__social">
        <a
          href="https://facebook.com/designbywillj"
          target="_blank"
          class="footer__social-link"
        >
          <img src="/svg/facebook.svg" alt="Facebook logo" />
        </a>

        <a
          href="https://instagram.com/designbywillj"
          target="_blank"
          class="footer__social-link"
        >
          <img src="/svg/instagram.svg" alt="Instagram logo" />
        </a>

        <a
          href="https://twitter.com/designbywillj"
          target="_blank"
          class="footer__social-link"
        >
          <img src="/svg/twitter.svg" alt="Twitter logo" />
        </a>

        <a
          href="https://dribbble.com/designbywillj"
          target="_blank"
          class="footer__social-link"
        >
          <img src="/svg/dribbble.svg" alt="Dribbble logo" />
        </a>

        <a
          href="https://linkedin.com/in/designbywillj"
          target="_blank"
          class="footer__social-link"
        >
          <img src="/svg/linkedin.svg" alt="LinkedIn logo" />
        </a>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style lang="scss">
@import '@/assets/scss/variables';

.footer {
  width: 100%;
  margin-top: 4rem;
  padding: 0 2rem 2rem;

  @media (min-width: $breakpoint--md) {
    margin-top: 12rem;
    padding: 0 4rem 4rem;
  }

  &__content {
    max-width: 75rem;
    margin: 0 auto;
    display: flex;
    flex-direction: column;

    @media (min-width: $breakpoint--md) {
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
    }
  }

  &__email {
    margin-bottom: 1rem;
    font-weight: 600;

    @media (min-width: $breakpoint--md) {
      margin-bottom: 0;
    }
  }

  &__social {
    display: flex;
    margin-left: -0.425rem;

    @media (min-width: $breakpoint--md) {
      margin-left: 0;
    }

    &-link {
      width: 2rem;
      height: 2rem;
      margin-right: 1rem;

      @media (min-width: $breakpoint--md) {
        margin-right: 0;
        margin-left: 1rem;
      }
    }
  }
}
</style>
