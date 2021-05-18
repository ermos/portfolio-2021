<template>
  <div>
    <Nuxt />
  </div>
</template>

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
  color: #fbae3c;
  font-weight: bold;
}
</style>
