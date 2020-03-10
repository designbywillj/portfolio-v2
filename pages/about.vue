<template>
  <article class="about">
    <div class="about__content">
      <section class="about__section">
        <h1>Hey, I'm Will.</h1>
        <p>
          I am from Central Kentucky, currently living in Nashville, Tennessee. I love
          solving difficult problems, researching, and designing impactful experiences
          that influence how a user interacts with their device, whether it is on a small
          or large scale. Understanding the needs and emotions of humans and tailoring to
          those aspects through great product experience is my passion.
        </p>
        <p>
          From a young age, art and design has always interested me. I used to draw
          various pieces of art, but I found myself mostly drawing buildings. My whole
          life, I have believed design was something I was destined for. My uncle was a
          tattoo artist, and my brother spent most of his time drawing and creating
          amazing work. Their passion for what they have done is what has drove me to find
          my passion in design.
        </p>
      </section>

      <section class="about__section">
        <h2>Focus</h2>
        <p>
          Since I started designing in March 2013, my focus has differed from branding and
          motion design to finally UX and product design. I have experience working on
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
          The journey in my design career so far since 2013 has been full of learning and
          growth. The first program I ever used was Cinema 4D. I was fascinated with
          letting my imagination take ahold of me when creating 3D scenes. I eventually
          introduced myself to Adobe products like Photoshop, Illustrator, After Effects,
          InDesign, and Premiere Pro.
        </p>
        <p>
          Once I started to dive into the UX world, I started to introduce myself to tools
          like Sketch, but I eventually fell in love with Figma. I spent my days before
          college researching the field and getting my feet wet, practicing data- and
          research-driven design.
        </p>
        <p>
          I have worked for various small remote-based startups like ConcurApp and
          playWEG, branding their product, designing experiences, or working on
          frontend-related tasks.
        </p>
        <p>
          I am currently a Creative Engineer at
          <a href="https://visualsbyimpulse.com" target="_blank">Visuals by Impulse</a>, a
          remote-based design studio who has worked with thousands of streamers and
          personalities. I create experiences for VBI's staff, front-facing clients, and
          consumers. Some of these projects include the
          <nuxt-link to="/case-study/vbi-crm-tool" target="_blank">VBI CRM Tool</nuxt-link
          >,
          <nuxt-link to="/case-study/vbi-website" target="_blank">VBI's Website</nuxt-link
          >, and the Stream Design Factory.
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
      </section>

      <hr />

      <section class="about__section">
        <h2>Let's Chat!</h2>
        <div class="about__cta">
          <a href="https://facebook.com/designbywillj" class="about__cta-link">
            <img src="/svg/facebook.svg" alt="Facebook logo" />
          </a>
          <a href="https://instagram.com/designbywillj" class="about__cta-link">
            <img src="/svg/instagram.svg" alt="Instagram logo" />
          </a>
          <a href="https://twitter.com/designbywillj" class="about__cta-link">
            <img src="/svg/twitter.svg" alt="Twitter logo" />
          </a>
          <a href="https://linkedin.com/in/designbywillj" class="about__cta-link">
            <img src="/svg/linkedin.svg" alt="LinkedIn logo" />
          </a>
        </div>
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

  &__cta {
    display: flex;
    flex-wrap: wrap;

    &-link {
      height: 3rem;
      margin-left: 1rem;

      &:first-child {
        margin-left: -0.5rem;
      }

      @media (min-width: $breakpoint--md) {
        height: 4rem;
      }

      img {
        width: 3rem;

        @media (min-width: $breakpoint--md) {
          width: 4rem;
        }
      }
    }
  }

  &__img {
    width: 100%;
  }
}
</style>
