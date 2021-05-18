<template>
  <div>
    <Welcome />
  </div>
</template>

<script>
import Welcome from '../components/Welcome'

export default {
  components: [Welcome],
}
</script>

<style>
/*.btn {*/
/*  position: relative;*/
/*  margin-top: var(--spacing-large);*/
/*  background: none;*/
/*  border: 2px solid #fff;*/
/*  border-radius: 0;*/
/*  padding: var(--spacing-medium);*/
/*  color: #fff;*/
/*  text-transform: uppercase;*/
/*  cursor: pointer;*/
/*}*/

/*.btn:after {*/
/*  content: '';*/
/*  position: absolute;*/
/*  z-index: -1;*/
/*  bottom: 0;*/
/*  left: 0;*/
/*  right: 0;*/
/*  width: 100%;*/
/*  background: #fbae3c;*/
/*  height: 0;*/
/*  transition: all 0.4s ease-in;*/
/*}*/

/*.btn:hover:after {*/
/*  height: 100%;*/
/*}*/

/*.btn svg {*/
/*  margin-left: var(--spacing-medium);*/
/*}*/

@keyframes home--bounce {
  0% {
    opacity: 0;
    transform: scale(0.5);
  }
  80% {
    opacity: 1;
    transform: scale(1.025);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

@keyframes home--fade-in {
  0% {
    opacity: 0;
    transform: scale(1.5);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

@keyframes home--fade-out {
  0% {
    opacity: 1;
    transform: scale(1);
  }
  100% {
    opacity: 0;
    transform: scale(1.5);
  }
}
</style>
