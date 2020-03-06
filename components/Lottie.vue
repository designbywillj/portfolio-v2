<template>
  <div class="lottie__wrapper">
    <div ref="lottieCanvas" class="lottie" />
  </div>
</template>

<script>
import lottie from 'lottie-web'

export default {
  name: 'Lottie',
  props: {
    name: {
      type: String,
      required: true
    },
    loop: {
      type: Boolean,
      default: true
    },
    autoplay: {
      type: Boolean,
      default: true
    },
    keep: {
      type: Boolean,
      default: false
    }
  },

  data() {
    return {
      animation: null
    }
  },

  mounted() {
    this.animation = lottie.loadAnimation({
      container: this.$refs.lottieCanvas,
      path: `/lottie/${this.name}.json`,
      renderer: 'svg',
      loop: this.loop,
      autoplay: this.autoplay,
      name: this.name
    })
    this.animation.addEventListener('complete', () => this.$emit('complete'))
    this.animation.addEventListener('loopComplete', () => this.$emit('loopComplete'))
  },

  beforeDestroy() {
    if (!this.keep) this.animation.destroy()
  }
}
</script>

<style lang="scss">
.lottie {
  width: 24rem;
  position: relative;

  &__wrapper {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }
}
</style>
