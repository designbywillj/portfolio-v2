<template>
  <footer class="footer">
    <div class="footer__content">
      <a href="mailto:hi@designbywillj.com" class="footer__email">hi@designbywillj.com</a>
      <div class="footer__social"></div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style lang="scss">
.footer {
  width: 100%;
  margin-top: 12rem;
  padding: 0 4rem 4rem;

  &__content {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
}
</style>
