<template>
  <header class="header">
    <nav>
      <nuxt-link to="/" class="header__logo">
        <Logo />
      </nuxt-link>
      <ul class="header__nav">
        <li>
          <nuxt-link to="/" class="header__nav-item">Work</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/about" class="header__nav-item">About</nuxt-link>
        </li>
        <li>
          <a
            href="https://drive.google.com/open?id=1MSItOhQLsdyca3GwFVlhzE-lQP3SPvGr"
            target="_blank"
            class="header__nav-item"
            >Resume</a
          >
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Header',
  components: {
    Logo: () => import('@/components/Logo')
  }
}
</script>

<style lang="scss">
@import '@/assets/scss/colors';

.header {
  width: 100%;
  margin-bottom: 8rem;
  padding: 4rem 4rem 0;

  nav {
    width: 100%;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__logo {
    height: 2rem;
  }

  &__nav {
    padding: 0;
    display: flex;
    list-style-type: none;

    &-item {
      margin-left: 2rem;
      padding: 0;
      color: $color--gray;
      line-height: 2rem;
      text-decoration: none;
      transition: color 0.25s ease-in-out;

      &.nuxt-link-exact-active {
        color: $color--black;
        font-weight: 600;
      }
    }
  }
}
</style>
