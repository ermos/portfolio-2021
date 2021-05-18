<template>
  <div id="home">
    <div class="home__content">
      <h1 class="logo home__logo">Kilian Smiti<span>.</span></h1>
      <p class="home__description">
        Welcome to my world, I am a <span>full-stack developer</span> living in
        <span>France</span>, scroll to find out more about me !
      </p>
      <div class="scroll-down--wrapper">
        <div class="scroll-down"></div>
      </div>
    </div>
    <div class="background home--background" />
  </div>
</template>

<script>
export default {
  name: 'Welcome',
}
</script>

<style>
.home--background {
  background: url('/images/1.svg');
  background-size: cover;
  animation: home--fade-in ease-in-out 2s 1 normal forwards;
  opacity: 0;
}

#home {
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  position: relative;
  overflow: hidden;
  height: 100vh;
  width: 100%;
}

.home__content {
  animation: home--bounce ease-in-out 0.25s 1 normal forwards;
  opacity: 0;
}

.logo {
  font-weight: bold;
  font-size: 8rem;
  color: #fff;
  font-family: 'Open Sans', sans-serif;
}

.home__description {
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
