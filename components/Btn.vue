<template>
  <button class="btn" @click="(e) => $emit('click', e)">
    <p><slot /></p>
  </button>
</template>

<script>
export default {
  name: 'Btn',
}
</script>

<style>
.btn {
  position: relative;
  margin-top: var(--spacing-large);
  background: none;
  border: 2px solid var(--sub-color);
  border-radius: 0;
  padding: var(--spacing-medium);
  color: var(--sub-color);
  text-transform: uppercase;
  cursor: pointer;
}

.btn p {
  position: relative;
  z-index: 2;
}

.btn:after {
  content: '';
  position: absolute;
  z-index: 1;
  bottom: 0;
  left: 0;
  right: 0;
  width: 100%;
  background: var(--sub-color);
  height: 0;
  transition: all 0.4s ease-in;
}

.btn:hover:after {
  height: 100%;
}

.btn:hover p {
  transition: all 0.6s ease-in;
  color: #fff;
}

.btn svg {
  margin-left: var(--spacing-medium);
}
</style>
