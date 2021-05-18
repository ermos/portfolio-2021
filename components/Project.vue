<template>
  <div id="project">
    <div class="project__content">
      <nav data-aos="fade" class="project__nav">
        <a class="nav__item active">Personal</a>
        <a class="nav__item">Professional</a>
      </nav>
      <div class="project__items">
        <div
          v-for="i in 10"
          :key="i"
          data-aos="flip-left"
          :data-aos-delay="i * 100"
          class="item"
        >
          <div class="item__logo--wrapper">
            <img
              class="item__logo"
              src="/images/project/itsnook_icon.png"
              alt="It's Nook logo"
            />
            <h3 class="item__title">It's Nook</h3>
            <p class="item__description">
              Pattern Editor for the video game Animal Crossing
            </p>
          </div>
          <img
            class="item__background"
            src="/images/project/itsnook.png"
            alt="it's nook application"
          />
        </div>
      </div>
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
}

#project {
  position: relative;
  overflow: hidden;
  height: 400px;
  width: 100%;
}

.project__content {
  height: 400px;
  display: flex;
  flex-direction: column;
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
  user-select: none;
}

.nav__item:hover {
  transition: all 0.4s ease-in;
  text-shadow: 0 0 10px rgba(0, 0, 0, 0.4);
}

.nav__item.active {
  color: var(--sub-color);
}

.project__items {
  flex: 1;
  display: flex;
  align-items: center;
  padding: var(--spacing-little) var(--spacing-little) var(--spacing-medium);
}

.item {
  position: relative;
  height: 100%;
  margin: var(--spacing-little);
  background-color: #adadad;
  /*max-width: 400px;*/
  min-width: 500px;
  width: 100%;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  cursor: pointer;
}

.item__logo--wrapper {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.item__logo {
  width: 80px;
  margin: var(--spacing-medium);
}

.item__title {
  font-family: 'Open Sans', sans-serif;
  color: var(--neutral-color);
  font-weight: bold;
  font-size: 3rem;
  text-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
}

.item__description {
  color: #fff;
  font-weight: bold;
  margin-top: 5px;
  max-width: 60%;
  text-shadow: 0 0 10px #000;
}

.item__background {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  z-index: -1;
  opacity: 0.4;
}

.item:hover .item__background {
  transition: all 0.4s ease-in;
  opacity: 0.8;
}

.item:hover .item__logo--wrapper {
  transition: all 0.4s ease-in;
  opacity: 0.5;
}
</style>
