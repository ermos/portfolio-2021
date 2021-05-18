<template>
  <div id="project">
    <div class="project__content">
      <nav data-aos="fade-in" class="project__nav">
        <a class="nav__item active">Personal</a>
        <a class="nav__item">Professional</a>
      </nav>
    </div>
    <div class="background project--background" />
  </div>
</template>

<script>
export default {
  name: 'Project',
  // data() {
  //   return {
  //   }
  // },
}
</script>

<style>
.project--background {
  background: url('/images/2.svg');
  background-size: cover;
  animation: project--fade-in ease-in-out 2s 1 normal forwards;
  opacity: 0;
}

#project {
  display: flex;
  position: relative;
  overflow: hidden;
  height: 400px;
  width: 100%;
}

.project__content {
  animation: project--bounce ease-in-out 0.25s 1 normal forwards;
  opacity: 0;
}

.project__nav {
  font-family: 'Open Sans', sans-serif;
  display: flex;
  padding: var(--spacing-little);
}

.nav__item {
  color: #868686;
  font-weight: bold;
  font-size: 2.5rem;
  padding: var(--spacing-little);
  cursor: pointer;
}

.nav__item.active {
  color: var(--sub-color);
}

.logo {
  font-weight: bold;
  font-size: 8rem;
  color: #fff;
  font-family: 'Open Sans', sans-serif;
}

.project__description {
  line-height: 1.5;
  font-size: 2rem;
  max-width: 600px;
  padding: 0 var(--spacing-medium);
  margin-top: var(--spacing-large);
}

.scroll-down--wrapper {
  position: relative;
  margin-top: var(--spacing-large);
}

.scroll-down {
  border: 2px solid #fff;
  border-radius: 20px;
  bottom: 60px;
  height: 50px;
  top: 0;
  left: 0;
  margin: 0 auto;
  position: absolute;
  right: 0;
  width: 30px;
}

.scroll-down::before {
  animation: scrollDownAnimation 2s infinite;
  background-color: #fff;
  border-radius: 100%;
  content: '';
  height: 6px;
  left: 0;
  margin: 0 auto;
  position: absolute;
  right: 0;
  top: 10px;
  width: 6px;
}

@keyframes project--bounce {
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

@keyframes project--fade-in {
  0% {
    opacity: 0;
    transform: scale(1.5);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

@keyframes project--fade-out {
  0% {
    opacity: 1;
    transform: scale(1);
  }
  100% {
    opacity: 0;
    transform: scale(1.5);
  }
}

@-moz-keyframes scrollDownAnimation {
  0% {
    opacity: 0;
    transform: translate(0, 0);
  }
  40% {
    opacity: 1;
  }
  80% {
    opacity: 0;
    transform: translate(0, 20px);
  }
  100% {
    opacity: 0;
  }
}
@-webkit-keyframes scrollDownAnimation {
  0% {
    opacity: 0;
    transform: translate(0, 0);
  }
  40% {
    opacity: 1;
  }
  80% {
    opacity: 0;
    transform: translate(0, 20px);
  }
  100% {
    opacity: 0;
  }
}
@-o-keyframes scrollDownAnimation {
  0% {
    opacity: 0;
    transform: translate(0, 0);
  }
  40% {
    opacity: 1;
  }
  80% {
    opacity: 0;
    transform: translate(0, 20px);
  }
  100% {
    opacity: 0;
  }
}
@keyframes scrollDownAnimation {
  0% {
    opacity: 0;
    transform: translate(0, 0);
  }
  40% {
    opacity: 1;
  }
  80% {
    opacity: 0;
    transform: translate(0, 20px);
  }
  100% {
    opacity: 0;
  }
}
</style>
