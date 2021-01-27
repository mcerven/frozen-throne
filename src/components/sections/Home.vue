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
      <h2 class="Home__title">{{title}}</h2>
      <p class="Home__subtitle">{{subtitle}}</p>
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
  name: 'Home',
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
    top: 0;
    height: 650px;
  }

  .Home__video {
    width: 100%;
    height: 100%;
    object-fit: cover;
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
    font-size: 1rem;
  }

  @media screen and (max-width: 600px) {
    .Home__content {
      font-size: 0.8rem;
    }
  }

  .Home__logo img {
    margin-top: 100px;
    max-width: 100%;
    user-select: none;
  }

  .Home__title, .Home__subtitle {
    margin: 2rem;
  }

  .Home__title {
    letter-spacing: 2px;
    text-shadow: 0 0 26px rgba(0, 0, 0, 1);
  }
  
  .Home__subtitle {
    color: var(--bg-secondary);
    text-transform: uppercase;
    font-size: 1.2em;
    font-weight: 600;
  }

  .Home__scroll-icon {
    position: absolute;
    bottom: 4em;
    width: 100%;
    display: flex;
    justify-content: center;
  }
</style>
