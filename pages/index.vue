<template>
  <div style="min-height: 300vh">
    <Welcome />
    <Project />
  </div>
</template>

<script>
import Welcome from '../components/Welcome'
import Project from '../components/Project'
import aos from '~/mixins/aos'

export default {
  components: [Welcome, Project],
  mixins: [aos],
}
</script>
