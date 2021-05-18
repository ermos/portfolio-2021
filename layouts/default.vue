<template>
  <div>
    <Nuxt />
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: this.title,
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: 'description',
          name: 'description',
          content: 'My custom description',
        },
      ],
    }
  },
}
</script>

<style>
#app {
  height: 100vh;
  display: flex;
  flex-direction: column;
}

.background {
  position: absolute;
  z-index: -1;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  width: 100%;
  height: 100%;
}

span {
  color: var(--neutral-color);
  font-weight: bold;
}
</style>
