<template>
  <div id="welcome">
    <div class="welcome__content">
      <h1 data-aos="fade" class="logo">Kilian Smiti<span>.</span></h1>
      <p data-aos="fade" class="welcome__description">
        Welcome to my world, I am a <span>{{ descriptionText }}</span>
        <br />
        living in <span>France</span>, scroll to find out more about me !
      </p>
      <div data-aos="fade-in" class="scroll-down--wrapper">
        <div class="scroll-down"></div>
      </div>
    </div>
    <div class="background welcome--background" />
  </div>
</template>

<script>
export default {
  name: 'Welcome',
  data() {
    return {
      currentDescription: 0,
      descriptionText: 'Full-stack Developer',
      descriptionList: [
        'Full-stack Developer',
        'Passionate',
        'Self-taught',
        'Designer',
        'Robot',
      ],
    }
  },
  mounted() {
    setTimeout(() => {
      this.switchDescription()
    }, 1000)
  },
  methods: {
    switchDescription() {
      if (this.currentDescription + 1 > this.descriptionList.length - 1) {
        this.currentDescription = 0
      } else {
        this.currentDescription++
      }

      this.writeDescription(false, this.descriptionText.length, 0)
    },
    writeDescription(write, length, i) {
      if (!write) {
        if (i < length) {
          this.descriptionText = this.descriptionText.slice(0, -1)
          i++
          setTimeout(() => {
            this.writeDescription(false, length, i)
          }, 50)
        } else {
          this.writeDescription(
            true,
            this.descriptionList[this.currentDescription].length,
            0
          )
        }
      } else if (i < length) {
        this.descriptionText =
          this.descriptionText +
          this.descriptionList[this.currentDescription].charAt(i)
        i++
        setTimeout(() => {
          this.writeDescription(true, length, i)
        }, 50)
      } else {
        setTimeout(() => {
          this.switchDescription()
        }, 1000)
      }
    },
  },
}
</script>

<style>
.welcome--background {
  background: url('/images/1.svg');
  background-size: cover;
  animation: welcome--fade-in ease-in-out 2s 1 normal forwards;
  opacity: 0;
}

#welcome {
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  position: relative;
  overflow: hidden;
  height: 100vh;
  width: 100%;
}

.welcome__content {
  animation: welcome--bounce ease-in-out 0.5s 1 normal forwards;
  opacity: 0;
}

.logo {
  font-weight: bold;
  font-size: 8rem;
  color: #fff;
  font-family: 'Open Sans', sans-serif;
}

.welcome__description {
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

@keyframes welcome--bounce {
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

@keyframes welcome--fade-in {
  0% {
    opacity: 0;
    transform: scale(1.5);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

@keyframes welcome--fade-out {
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
