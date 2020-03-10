<template>
  <article class="about">
    <div class="about__content">
      <section class="about__section">
        <h1>Hey, I'm Will.</h1>
        <p>
          I am from Central Kentucky, currently living in Nashville, Tennessee. I love
          working on various design projects, whether it be creating brands or designing
          sites and apps. I've been designing and playing with code since I was twelve.
          While I listen to a lot of music, I spend most of my time at my desk working on
          personal projects and other various projects.
        </p>
      </section>

      <section class="about__section">
        <h2>Focus</h2>
        <p>
          My primary focus is in UX and product design. I have experience working on
          branding projects, but I have always found to love solving problems that relate
          directly to users and their needs. Designing data- and research-driven products
          is a passion of mine, and I am always learning and growing my skills as a
          designer in each project I am a part of.
        </p>
        <p>
          When it comes to product design, my favorite part of the process is developing
          and iterating on the product's design system based on research and common
          elements. Building out components and assets and solving how these will be used
          in various views is one small part of the whole process that I love doing.
        </p>
      </section>

      <section class="about__section">
        <h2>Experience</h2>
        <p>
          I am currently a Creative Engineer at Visuals by Impulse, a remote-based design
          studio who has worked with thousands of streamers and personalities. I create
          experiences for VBI's staff, front-facing clients, and consumers. Some of these
          projects include the VBI CRM Tool, VBI's Website, and the Stream Design Factory.
        </p>
        <p>
          My responsibilities at VBI include UX research and design and frontend
          development tasks. Focusing on driving up sales and overall engagement through
          thoughtful UX choices is one of my major roles for VBI's site. For VBI's CRM
          Tool, the design process was very iterative, which led to a year long effort to
          create a proprietary CRM tool that ultimately streamlined the process of
          managing projects, clients, and team members, allowing users to complete tasks
          more efficiently.
        </p>
        <p>
          I am currently a Creative Engineer at Visuals by Impulse, a remote-based design
          studio who has worked with thousands of streamers and personalities. I create
          experiences for VBI's staff, front-facing clients, and consumers. Some of these
          projects include the VBI CRM Tool, VBI's Website, and the Stream Design Factory.
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
      title: 'About | Will Johnson - Graphic, Motion, & UX Designer',
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
@import '@/assets/scss/variables';

.about {
  display: flex;
  flex-direction: column-reverse;

  @media (min-width: $breakpoint--md) {
    flex-direction: row;
  }

  &__content {
    flex: 0 0 100%;

    @media (min-width: $breakpoint--md) {
      flex: 0 1 60%;
      padding-right: 4rem;
    }
  }

  &__section {
    width: 100%;
  }

  &__feature {
    flex: 0 0 100%;
    margin-bottom: 4rem;

    @media (min-width: $breakpoint--md) {
      flex: 0 1 40%;
      margin-bottom: 0;
      padding-left: 4rem;
    }
  }

  &__img {
    width: 100%;
  }
}
</style>
