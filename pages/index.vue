<template>
  <div>
    <Welcome />
    <AboutMe />
    <Project />
    <Footer />
  </div>
</template>

<script>
import Welcome from '../components/Welcome'
import Project from '../components/Project'
import AboutMe from '../components/AboutMe'
import Footer from '../components/Footer'
import aos from '~/mixins/aos'

export default {
  components: [Welcome, Project, AboutMe, Footer],
  mixins: [aos],
}
</script>
