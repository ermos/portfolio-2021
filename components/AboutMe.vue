<template>
  <main class="portfolio__body">
    <section class="portfolio__content">
      <aside class="portfolio__aside">
        <img
          data-aos="zoom-in"
          class="portfolio__avatar"
          alt="picture of Kilian SMITI"
          src="/images/avatar.jpeg"
        />
        <h1 data-aos="fade" class="portfolio__full-name">Kilian SMITI</h1>
        <p data-aos="fade" class="portfolio__job">Full-Stack Developer</p>
      </aside>
      <article class="portfolio__article">
        <h2 data-aos="fade-up" class="biography__title">Hey ! 👋</h2>
        <p data-aos="fade-up" class="biography__p">
          I'm <b>Kilian SMITI</b>, a french developer passionate about web
          technologies since his childhood. I started building websites when I
          was ten year old and I decided to make it my job.
        </p>
        <p data-aos="fade-up" class="biography__p">
          Currently, I'm <b>Full-Stack Developer</b> for <b>Free (Iliad)</b> 🚀,
          one of the main French telecommunications operators. I work on many
          internal applications, whether it is on invoicing tools, or civil
          engineering management tools, I have no trouble getting to grips with
          a subject.
        </p>
        <p data-aos="fade-up" class="biography__p">
          I master many langage and framework, for the front-end, I master
          <b>HTML</b>, <b>CSS</b> (with pre-processor like <b>Sass</b>),
          <b>Javascript</b> and some framework like <b>Vue.js</b>,
          <b>React</b> and <b>Electron</b>. For back-end langages, I master
          <b>Golang</b>, <b>PHP</b>, <b>Node.js</b> and some framework specialy
          in PHP like <b>Symfony</b> and <b>Laravel</b>.
        </p>
        <p data-aos="fade-up" class="biography__p">
          I'm also working with several tool like <b>Docker</b>, <b>Webpack</b>,
          <b>Typescript</b>, <b>ESLint</b> and <b>Git</b>.
        </p>
      </article>
    </section>
  </main>
</template>

<script>
export default {
  name: 'AboutMe',
}
</script>

<style>
.portfolio__body {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  background-color: #fff;
  color: #494949;
  font-family: Arial, -apple-system, BlinkMacSystemFont, segoe ui, Roboto,
    Oxygen-Sans, Ubuntu, Cantarell, helvetica neue, sans-serif;
}

.portfolio__content {
  width: 100%;
  max-width: var(--interface-size);
  box-sizing: border-box;
  padding: 50px 20px 20px;
  margin: auto;
  display: flex;
  justify-content: space-between;
}

.portfolio__aside {
  width: calc(30% - 30px);
  text-align: center;
}

.portfolio__article {
  width: calc(70% - 30px);
}

.portfolio__avatar {
  width: 20rem;
  border-radius: 50%;
}

.portfolio__full-name {
  margin-top: 20px;
  font-size: 3.5rem;
  color: #000;
  font-weight: bold;
}

.portfolio__job {
  margin-top: 10px;
  font-size: 2.3rem;
  color: #737373;
}

.biography__title {
  font-size: 5rem;
}

.biography__p {
  font-size: 2rem;
  margin-top: 20px;
  line-height: 2;
}

.biography__p b {
  background-color: rgba(251, 174, 60, 0.2);
  box-sizing: border-box;
  padding: 0 5px;
  color: var(--neutral-color);
}

@media screen and (max-width: 800px) {
  .portfolio__content {
    flex-direction: column;
    align-items: center;
  }

  .portfolio__article {
    margin-top: 50px;
    text-align: center;
  }

  .portfolio__aside {
    width: 100%;
  }
}
</style>
