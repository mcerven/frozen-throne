<template>
  <section id="home">
    <div class="Home__bg">
      <video ref="video" class="Home__video" autoplay look muted>
        <source src="../../assets/videos/wow-snow.mp4" />
      </video>
      <div class="Home__gradient"></div>
    </div>
    <div class="Home__content">
      <img src="../../assets/images/ft-logo.png" alt="Frozen Throne" />
      <header>
        <h2 class="Home__title">{{title}}</h2>
      </header>
      <p class="Home__subtitle">{{subtitle}}</p>
      <DiscordButton></DiscordButton>
    </div>
  </section>
</template>

<script>
import { onMounted, ref } from 'vue';
import DiscordButton from '../discord-button';

export default {
  components: { DiscordButton },
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
    background: linear-gradient(rgba(0, 0, 0, 0.1) 35%, var(--bg-primary));
  }

  .Home__content {
    position: absolute;
    top: 30%;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    text-align: center;
    font-size: 1.1rem;
  }

  .Home__title {
    margin: 1.2rem;
    font-size: 2rem;
  }
  .Home__subtitle {
    color: var(--text-secondary);
    text-transform: uppercase;
    margin: 1.2rem;
    font-size: 1.5rem;
  }
</style>
