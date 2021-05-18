<template>
  <div id="project">
    <div class="project__content">
      <h2 data-aos="fade" class="project__title">Personal Projects</h2>
      <div class="project__items">
        <div v-show="isPrev" class="project__btn project__prev" @click="goPrev">
          <fa icon="angle-left" />
        </div>
        <div v-show="isNext" class="project__btn project__next" @click="goNext">
          <fa icon="angle-right" />
        </div>
        <div
          class="items--wrapper"
          :style="'transform: translateX(-' + position + 'px)'"
        >
          <div
            v-for="(item, i) in list"
            :key="i"
            class="item"
            :class="current === i ? 'active' : ''"
            @click="current = i"
          >
            <div class="item__logo--wrapper">
              <img
                width="auto"
                height="auto"
                class="item__logo"
                :src="item.logo_url"
                :alt="`${item.title}'s logo`"
              />
              <h3 class="item__title">{{ item.title }}</h3>
              <p class="item__description">
                {{ item.description }}
              </p>
            </div>
            <img
              width="auto"
              height="auto"
              class="item__background"
              :src="item.background_url"
              :alt="`${item.title}'s application screen`"
            />
          </div>
        </div>
      </div>
    </div>
    <article class="project__explain">
      <h3 data-aos="fade-left" class="explain__title">
        {{ list[current].title }}
      </h3>
      <p data-aos="fade-left" class="explain__description">
        {{ list[current].description }}
      </p>
      <p data-aos="fade-left" class="explain__stack">
        <b>Stack :</b> {{ list[current].stack }}
      </p>
      <p
        v-for="(t, i) in list[current].text"
        :key="i"
        data-aos="fade-left"
        class="explain__paragraphe"
      >
        {{ t }}
      </p>
      <a
        v-if="list[current].url != null"
        class="explain__link"
        :href="list[current].url"
      >
        <Btn data-aos="fade-left" class="explain__btn"
          >Go on {{ list[current].title }}</Btn
        >
      </a>
    </article>
    <div class="background project--background" />
  </div>
</template>

<script>
import Btn from '../components/Btn'

export default {
  name: 'Project',
  components: [Btn],
  data() {
    return {
      current: 0,
      list: [
        {
          title: "It's Nook",
          stack: 'Nuxt.js, Golang, Gitlab-ci, Docker',
          description: 'Pattern Editor for the video game Animal Crossing',
          logo_url: '/images/project/itsnook_icon.png',
          background_url: '/images/project/itsnook.jpg',
          url: 'https://itsnook.com/#/editor',
          text: [
            `The idea behind this application was to bring back a breath of freshness
            in the world of pattern editors on Animal Crossing. Most being aging
            whether it is ergonomically or in terms of features, I decided to create
            my own editor.`,
            `It's Nook is therefore a mix between the existing pattern editors and
        digital drawing tools such as Paint or Photoshop, the interface is also
        strongly inspired by the latter.`,
            `This project allowed me to discover a lot of concept in the image
        processing, it is also one of my first highly interactive web interface.`,
          ],
        },
        {
          title: 'FortnitePredict',
          stack: 'Symfony 4',
          description: 'Calculate your progress in your battle pass',
          logo_url: '/images/project/fortnitepredict_icon.png',
          background_url: '/images/project/fortnitepredict.jpg',
          url: null,
          text: [
            `FortnitePredict allows you to calculate the number of games on the Fortnite game
            necessary to reach the final level of your battle pass
            following an algorithm based on the player's profile.`,
            `Following the overhaul of the Fortnite system, the tool no longer being useful, has been stopped.`,
          ],
        },
        {
          title: 'HSFactory',
          stack: 'Pawn',
          description: 'Counter-Strike Training Platform',
          logo_url: '/images/project/hsfactory_icon.png',
          background_url: '/images/project/hsfactory.jpg',
          url: 'https://hsfactory.net/',
          text: [
            `HSFactory is a training platform based on the counter-strike game, it has a multitude of servers on different game modes.`,
            `I was in charge for several years of designing and maintaining game server plugins.`,
          ],
        },
        {
          title: 'MyGuilde',
          stack: 'Symfony 4, Gitlab-ci',
          description: 'Site generator for gaming guilds/clans',
          logo_url: '/images/project/myguilde_icon.png',
          background_url: '/images/project/myguilde.jpg',
          url: null,
          text: [
            `MyGuilde allows you to generate guild sites with all the essentials
            that a video game guild needed: a forum, member management and an article system.`,
            `The main target was the DOFUS game guilds, it was common to see guilds create their own sites,
            unfortunately it was not within the reach of everyone, this is where MyGuilde came into play.`,
            `Due to lack of time and money as well as the activity which was declining, the project was not maintained.`,
          ],
        },
        {
          title: 'SonoHabbo',
          stack: 'PHP',
          description: 'Web radio based on HABBO game',
          logo_url: '/images/project/sonohabbo_icon.png',
          background_url: '/images/project/sonohabbo.jpg',
          url: null,
          text: [
            `SonoHabbo is a web-radio taking up the concept of SonoZone by integrating the universe of HABBO around it.`,
            `The web radio was equipped with a web radio, an article system as well as various tools related to the game.`,
            `Due to lack of time from every member, the project was not maintained.`,
          ],
        },
      ],
      itemWidth: 400,
      projects: null,
      wrapper: null,
      position: 0,
      isNext: true,
      isPrev: false,
    }
  },
  mounted() {
    this.projects = document.querySelector('.project__items')
    this.wrapper = document.querySelector('.items--wrapper')
    const size = this.projects.offsetWidth
    const maxSize = this.projects.scrollWidth
    if (maxSize <= size) {
      this.isNext = false
    }
  },
  methods: {
    goNext() {
      const size =
        this.projects.offsetWidth > 600 ? 600 : this.projects.offsetWidth
      const maxSize = this.wrapper.scrollWidth
      this.isPrev = true
      if (this.position + size - 100 >= maxSize - size) {
        this.isNext = false
        this.position = maxSize - size
        return
      }
      this.position = this.position + size - 100
    },
    goPrev() {
      const size =
        this.projects.offsetWidth > 400 ? 400 : this.projects.offsetWidth
      this.isNext = true
      if (this.position - size - 100 < 0) {
        this.isPrev = false
        this.position = 0
        return
      }
      this.position = this.position - size - 100
    },
  },
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
  width: 100%;
}

.project__content {
  display: flex;
  flex-direction: column;
}

.project__title {
  font-family: 'Open Sans', sans-serif;
  display: flex;
  padding: var(--spacing-medium);
  color: var(--sub-color);
  font-weight: bold;
  font-size: 2.5rem;
  user-select: none;
}

.project__items {
  flex: 1;
  display: flex;
  align-items: center;
  padding: var(--spacing-little) var(--spacing-little) var(--spacing-medium);
  position: relative;
}

.items--wrapper {
  display: flex;
  flex: 1;
  transition: all 0.5s ease-in;
}

.item {
  position: relative;
  margin: var(--spacing-little);
  background-color: #adadad;
  width: 400px;
  height: 250px;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  cursor: pointer;
  user-select: none;
}

.item.active {
  box-shadow: 0 0 10px var(--sub-color);
  cursor: initial;
}

.item.active .item__background {
  opacity: 0.6;
}

.item__logo--wrapper {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  position: relative;
  z-index: 2;
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
  width: 100%;
  height: 100%;
  z-index: 1;
  opacity: 0.4;
}

.item:hover .item__background {
  transition: all 0.4s ease-in;
  opacity: 0.6;
}

.project__btn {
  position: absolute;
  top: 50%;
  margin-top: -25px;
  height: 50px;
  width: 50px;
  cursor: pointer;
  color: var(--neutral-color);
  z-index: 5;
  display: flex;
  align-items: center;
  justify-content: center;
}

.project__btn svg {
  font-size: 5rem;
}

.project__btn:hover {
  transition: background-color 0.2s ease-in;
  background-color: var(--sub-color);
}

.project__btn:active {
  transition: initial;
  background-color: var(--sub-color-dark-1);
}

.project__next {
  right: 0;
}

.project__prev {
  left: 0;
}

.project__explain {
  padding: var(--spacing-little) var(--spacing-little) var(--spacing-large);
  margin: auto;
  color: #474747;
  width: calc(70% - 30px);
}

.explain__title {
  font-family: 'Open Sans', sans-serif;
  color: var(--sub-color);
  font-weight: bold;
  font-size: 5rem;
  padding: var(--spacing-little) var(--spacing-little) 0;
}

.explain__description {
  font-weight: bold;
  margin-top: 5px;
  padding: 0 var(--spacing-little) var(--spacing-little);
}

.explain__stack {
  font-size: 1.5rem;
  margin-top: 5px;
  padding: 0 var(--spacing-little) var(--spacing-little);
  color: #282828;
}

.explain__stack b {
  color: #323232;
  font-weight: bold;
}

.explain__paragraphe {
  font-size: 2rem;
  margin-top: 20px;
  line-height: 2;
  padding: var(--spacing-little);
}

.explain__link {
  text-decoration: none;
  color: inherit;
}

.explain__btn {
  margin: var(--spacing-little) auto;
  display: block;
}
</style>
