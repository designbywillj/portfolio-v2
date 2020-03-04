<template>
  <article class="about">
    <div class="about__content">
      <section class="about__section">
        <h1>Hey, I'm Will.</h1>
        <p>
          I'm from Central Kentucky, currently living in Nashville, Tennessee. I love
          working on various design projects, whether it be creating brands or designing
          sites and apps. I've been designing and playing with code since I was twelve.
          While I listen to a lot of music, I spend most of my time at my desk working on
          personal projects and other various projects.
        </p>
      </section>

      <section class="about__section">
        <h2>Focus</h2>
        <p>
          I'm from Central Kentucky, currently living in Nashville, Tennessee. I love
          working on various design projects, whether it be creating brands or designing
          sites and apps. I've been designing and playing with code since I was twelve.
          While I listen to a lot of music, I spend most of my time at my desk working on
          personal projects and other various projects.
        </p>
      </section>

      <section class="about__section">
        <h2>Experience</h2>
        <p>
          I am currently a UX Designer at Visuals by Impulse, a remote-based design studio
          who has worked with thousands of streamers big and small. I create experiences
          for VBI's staff, front-facing clients, and anyone who uses VBI's products,
          whether it be the portal or the new Stream Design Factory app on the Streamlabs
          OBS app store.
        </p>
      </section>

      <hr />

      <section class="about__section">
        <h2>Let's Chat!</h2>
        <p>
          I am currently a UX Designer at Visuals by Impulse, a remote-based design studio
          who has worked with thousands of streamers big and small. I create experiences
          for VBI's staff, front-facing clients, and anyone who uses VBI's products,
          whether it be the portal or the new Stream Design Factory app on the Streamlabs
          OBS app store.
        </p>
      </section>
    </div>
    <aside class="about__feature">
      <img src="/img/about_will_johnson.jpg" class="about__img" />
    </aside>
  </article>
</template>

<script>
export default {
  head() {
    return {
      title: 'About | Will Johnson - Graphic, Motion, and UX Designer',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Put an about description here'
        }
      ]
    }
  }
}
</script>

<style lang="scss">
.about {
  display: flex;

  &__content {
    flex: 0 1 60%;
    padding-right: 4rem;
  }

  &__section {
    width: 100%;
  }

  &__feature {
    flex: 0 1 40%;
    padding-left: 4rem;
  }

  &__img {
    width: 100%;
    position: sticky;
    top: 4rem;
  }
}
</style>
