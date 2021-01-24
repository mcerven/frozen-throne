<template>
  <section id="home">
    <div class="Home__bg">
      <video ref="video" class="Home__video" autoplay look muted>
        <source src="../../assets/videos/wow-snow.mp4" />
      </video>
      <div class="Home__gradient"></div>
    </div>
    <div class="Home__content">
      <div class="Home__logo">
        <img src="../../assets/images/ft-logo.png" alt="Frozen Throne" />
      </div>
      <div>
        <h2 class="Home__title">{{title}}</h2>
      </div>
      <div class="Home__subtitle">
        <p>{{subtitle}}</p>
      </div>
      <div class="Home__button">
        <DiscordButton></DiscordButton>
      </div>
    </div>
    <div class="Home__scroll-icon">
      <ScrollIcon width="50" />
    </div>
  </section>
</template>

<script>
import { onMounted, ref } from 'vue';
import DiscordButton from '../social-media/DiscordButton.vue';
import ScrollIcon from '../atomic/icons/ScrollIcon.vue';

export default {
  components: {
    DiscordButton,
    ScrollIcon,
  },
  props: {
    title: String,
    subtitle: String,
  },
  setup() {
    const video = ref(null);

    onMounted(() => {
      video.value.addEventListener('ended', restartVideo, false);
    });

    function restartVideo() {
      video.value.currentTime = 0.1; //setting to zero breaks iOS 3.2, the value won't update, values smaller than 0.1 was causing bug as well.
      video.value.play();
    }

    return {
      video,
    };
  }
}
</script>

<style scoped>
  .Home__bg {
    position: relative;
  }

  .Home__video {
    width: 100%;
  }

  .Home__gradient {
    position: absolute;
    bottom: 0;
    left: 0;
    height: 100%;
    width: 100%;
    background: linear-gradient(to bottom, rgba(0, 0, 0, 0.25) 35%, var(--bg-primary));
  }

  .Home__content {
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    text-align: center;
    font-size: 1.1rem;
  }

  .Home__logo {
    margin-top: 100px;
  }

  .Home__title {
    font-size: 2.1rem;
    letter-spacing: 2px;
    text-shadow: 0 0 26px rgba(0, 0, 0, 1);
  }
  
  .Home__subtitle {
    margin: 2rem;
    color: var(--bg-secondary);
    text-transform: uppercase;
    font-size: 1.2rem;
    font-weight: 600;
  }

  .Home__button {
    margin: 6rem;
  }

  .Home__scroll-icon {
    position: absolute;
    bottom: 4em;
    width: 100%;
    display: flex;
    justify-content: center;
  }
</style>
