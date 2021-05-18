<template>
  <div style="min-height: 500vh">
    <Welcome />
    <AboutMe />
    <Project />
  </div>
</template>

<script>
import Welcome from '../components/Welcome'
import Project from '../components/Project'
import AboutMe from '../components/AboutMe'
import aos from '~/mixins/aos'

export default {
  components: [Welcome, Project, AboutMe],
  mixins: [aos],
}
</script>
