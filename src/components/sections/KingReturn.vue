<template>
  <section id="king">
    <header>
      <h2>{{title}}</h2>
    </header>
    <div class="KingReturn">
      <div class="KingReturn__cinematic">
        <iframe
          :title="title"
          :src="videoUrl"
          frameBorder="0"
          allowFullScreen
        />
      </div>
    </div>
    <Footer :copyright="copyright" />
  </section>
</template>

<script>
import Footer from '../footer';

export default {
  name: 'KingReturn',
  components: {
    Footer,
  },
  props: {
    title: String,
    videoUrl: String,
    copyright: String,
  },
}
</script>

<style>
  .KingReturn {
    max-width: var(--page-max-width);
    margin: 0 auto;
  }

  .KingReturn__cinematic {
    display: flex;
    justify-content: center;
    padding: 0 10px;
  }

  .KingReturn__cinematic iframe {
    width: 800px;
    height: 450px;
  }

  @media
    screen and (max-width: 850px),
    screen and (max-height: 800px) {
    .KingReturn__cinematic iframe {
      width: 500px;
      height: 283px;
    }
  }

  @media
    screen and (max-width: 450px) {
    .KingReturn__cinematic iframe {
      width: 300px;
      height: 170px;
    }
  }
</style>